pipeline {
    agent any

    environment {
        APP_NAME = 'GradeBookApp'
        APP_VERSION = '2.0.0'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Fardin-Faruq/student-custom-environment.git'
            }
        }

        stage('Show App Info') {
            steps {
                echo "Building ${env.APP_NAME}, version ${env.APP_VERSION}"
            }
        }

        stage('Build') {
            steps {
                bat 'python -m py_compile app.py'
                echo "${env.APP_NAME} version ${env.APP_VERSION} compiled successfully."
            }
        }

        stage('Compare Variables') {
            steps {
                echo "Custom APP_NAME: ${env.APP_NAME}"
                echo "Custom APP_VERSION: ${env.APP_VERSION}"
                echo "Built-in BUILD_NUMBER: ${env.BUILD_NUMBER}"
                echo "Built-in WORKSPACE: ${env.WORKSPACE}"
            }
        }
    }
}