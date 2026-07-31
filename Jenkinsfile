pipeline {

    agent any

    stages {

        stage('Checkout') {
    steps {
        git 'https://github.com/nisharanipadhy14-hub/DevOps-Lab.git'
    }
}

        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Build') {
            steps {
                bat 'python app.py'
            }
        }

        stage('Test') {
            steps {
                bat 'pytest --junitxml=test-results.xml'
            }
        }
    }

    post {
        always {
            junit 'test-results.xml'
        }
    }
}
