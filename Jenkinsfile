pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your Git repository
                bat 'git clone https://github.com/VladimirMilchev/Student-Registry-App-Jenkins'
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
