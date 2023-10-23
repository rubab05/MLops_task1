pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

    stage('Install Requirements') {
        steps {
                bat 'C:\\Path\\To\\Python3\\python --version'
                bat 'C:\\Path\\To\\Python3\\pip install --user -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'python3 app.py'
            }
        }
    }
}
