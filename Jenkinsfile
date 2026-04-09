pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat '"C:\\Program Files (x86)\\Python39\\python.exe" -m pip install -r requirements.txt'
            }
        }

        stage('Run App') {
            steps {
                bat 'start /B "" "C:\\Program Files (x86)\\Python39\\python.exe" app.py'
            }
        }

        stage('Test') {
           steps {
              bat 'powershell -Command "Invoke-WebRequest http://localhost:5000 -UseBasicParsing"'
            }
        }
    }
}