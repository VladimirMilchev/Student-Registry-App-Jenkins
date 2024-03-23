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
        stage('Check for Security Vulnerabilities') {
            steps {
                // Install Node.js dependencies using npm
                bat 'npm audit'
            }
        }
        stage('Run Tests') {
            steps {
                // Run tests using npm
                bat 'npm test'
            }
        }
                stage('Cleanup') {
            steps {
                // Изтриване на свалените файлове
                bat 'rmdir /s /q Student-Registry-App-Jenkins' // За Windows
                // sh 'rm -rf Student-Registry-App-Jenkins' // За Unix/Linux
            }
        }
    }
}
