pipeline {
    agent any
    environment {
        PYTHON_EXECUTABLE = 'C:\\path\\to\\python.exe' // Replace with the actual path to your Python executable
        GIT_CREDENTIALS_ID = 'rubab05' // Replace with your Git credentials ID
    }
    stages {
        stage('Checkout') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: env.GIT_CREDENTIALS_ID, usernameVariable: 'GIT_USERNAME', passwordVariable: 'GIT_PASSWORD')]) {
                        bat "git config credential.username ${GIT_USERNAME}"
                        bat "git config credential.helper 'store --file=~/.git-credentials'"
                        bat 'git.exe rev-parse --resolve-git-dir .git'
                        checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: env.GIT_CREDENTIALS_ID, url: 'https://github.com/rubab05/MLops_task1.git']])
                    }
                }
            }
        }
        stage('Install Requirements') {
            steps {
                bat "${env.PYTHON_EXECUTABLE} --version"
                bat "${env.PYTHON_EXECUTABLE} -m pip install --user -r requirements.txt"
            }
        }
        stage('Run Tests') {
            steps {
                bat "${env.PYTHON_EXECUTABLE} app.py"
            }
        }
        // Add more stages as needed
    }
}
