pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'py -m pip install -r requirements.txt'
            }
        }

        stage('Build') {
            steps {
                bat 'py app.py'
            }
        }

        stage('Test') {
            steps {
                bat 'py -m pytest --junitxml=test-results.xml'
            }
        }
    }

    post {
        always {
            junit allowEmptyResults: true, testResults: 'test-results.xml'
        }
    }
}
