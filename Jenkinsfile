pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                script {
                    if (!fileExists('Student-Registry-App-Jenkins')) {
                        // Ако директорията не съществува, изпълнете клонирането
                        git 'https://github.com/VladimirMilchev/Student-Registry-App-Jenkins'
                    } else {
                        // Ако директорията съществува, пропуснете стъпката
                        echo 'Directory already exists, skipping git clone.'
                    }
                }
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies using npm
                bat 'npm install'
            }
        }
        stage('Start Application') {
            steps {
                // Start your Node.js application (if needed)
                // Example assuming your entry point is app.js
                bat 'start /B npm start' // /B - стартиране на процеса във фонов режим
                bat 'timeout /t 10 /nobreak' // Спиране на процеса след 10 секунди
                bat 'taskkill /F /IM node.exe'
            }
        }
        stage('Run Tests') {
            steps {
                // Run tests using npm
                bat 'npm test'
            }
        }
    }
}
