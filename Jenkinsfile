pipeline {
    agent any
    environment {
        APP_NAME = 'GradeBookApp'
        APP_VERSION = '2.0.0'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Show App Info') {
            steps {
                echo "Building ${env.APP_NAME}, version ${env.APP_VERSION}"
            }
        }
        stage('Build') {
            steps {
                // Change 'bat' to 'sh' if your Jenkins server runs on Linux/Mac
                bat 'python -m py_compile app.py'
                echo "${env.APP_NAME} version ${env.APP_VERSION} compiled successfully."
            }
        }
    }
}
