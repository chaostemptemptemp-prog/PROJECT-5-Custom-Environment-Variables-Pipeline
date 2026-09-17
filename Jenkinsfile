pipeline {
    agent any
    environment {
        APP_NAME = 'GradeBookApp'
        APP_VERSION = '2.0.0'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '**']], extensions: [],
                userRemoteConfigs: [[url: 'https://github.com/chaostemptemptemp-prog/PROJECT-5-Custom-Environment-Variables-Pipeline.git']])
            }
        }
        stage('Show App Info') {
            steps {
                echo "Building ${env.APP_NAME}, version ${env.APP_VERSION}"
            }
        }
        stage ('Build') {
            steps {
                bat 'python -m py_compile app.py'
                echo "${env.APP_NAME} version ${env.APP_VERSION} compiled successfully."
            }
        }
    }
}