pipeline {

    agent any

    stages {

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
            junit allowEmptyResults: true, testResults: 'test-results.xml'
        }
    }
}
