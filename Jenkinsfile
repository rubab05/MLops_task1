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
                //bat 'python3 --version'
                //bat 'pip3 install --user -r requirements.txt'
                echo "hello world"
            }
        }
        

        stage('Groovy'){
            steps {
                script {
                    t = load 'task7.groovy'
                    t.func('production')
                }
            }
        }
    }
}
