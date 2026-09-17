pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/DharukDharshan-10/Jenkins-Project-3.git'
            }
        }

        stage('Parallel Checks') {
            parallel {

                stage('Frontend Check') {
                    steps {
                        bat 'bat '"C:\\Users\\admin\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" frontend_check.py''
                    }
                }

                stage('Backend Check') {
                    steps {
                        bat 'bat '"C:\\Users\\admin\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" backend_check.py''
                    }
                }
            }
        }

        stage('Summary') {
            steps {
                echo 'Both frontend and backend checks are complete.'
            }
        }
    }
}
