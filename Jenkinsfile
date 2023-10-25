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
                echo 'hello world'
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
