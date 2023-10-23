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
                bat 'python3 --version'
                bat 'pip3 install --user -r requirements.txt'
            }
        }
        
        stage('Run Tests') {
            steps {
                //bat 'python3 app.py'
                echo 'hello world'
            }
        }
    }
}
