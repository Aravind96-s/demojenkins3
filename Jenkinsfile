pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Aravind96-s/demojenkins3.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'python -m pip install -r requirements.txt'
            }
        }

        stage('Kill Old App') {
            steps {
                bat 'taskkill /F /IM python.exe || echo No process running'
            }
        }

        stage('Run App') {
            steps {
                bat 'start /B python app.py'
            }
        }

        stage('Test') {
            steps {
                bat 'curl http://localhost:5000'
            }
        }
    }
}