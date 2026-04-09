pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat '"C:\\Program Files (x86)\\Python39\\python.exe" -m pip install -r requirements.txt'
            }
        }

        stage('Kill Old App') {
            steps {
                bat 'taskkill /F /IM python.exe || echo No process running'
            }
        }

        stage('Run App') {
            steps {
                bat 'start /B "" "C:\\Users\\Aravind\\AppData\\Local\\Programs\\Python\\Python39\\python.exe" app.py'
            }
        }

        stage('Test') {
            steps {
                bat 'curl http://localhost:5000'
            }
        }
    }
}