pipeline {
    agent any

    tools {
        nodejs 'NodeJS' // Name you gave to the NodeJS installation
    }

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/HariharanAI/My-Bank.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    sh 'npm test'
                }
            }
        }

        stage('Build Application') {
            steps {
                script {
                    sh 'npm run build'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }
        failure {
            echo 'There was an error in the build process.'
        }
    }
}
