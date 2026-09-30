pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
                echo 'Source code checkout completed'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the Python application...'
                bat 'python -m py_compile src\\app.py'
            }
        }

        stage('Test') {
    steps {
        echo 'Installing Python dependencies...'
        bat 'python -m pip install -r requirements.txt'

        echo 'Running pytest...'
        bat 'python -m pytest -v'
    }
}

        stage('Result') {
            steps {
                echo 'CI Pipeline completed successfully!'
            }
        }
    }
}