pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your Git repository
                bat 'git clone https://github.com/VladimirMilchev/Student-Registry-App-Jenkins'
            }
        }
        stage('Setup Node.js') {
            steps {
                // Setup Node.js using NVM'

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
                bat 'node app.js'
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
