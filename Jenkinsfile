pipeline {
    agent any

    stages {

        stage('Check Python') {
            steps {
                bat '"C:\\Python314\\python.exe" --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '"C:\\Python314\\python.exe" -m pip install -r requirements.txt'
            }
        }

        stage('Build') {
            steps {
                bat '"C:\\Python314\\python.exe" app.py'
            }
        }

        stage('Test') {
            steps {
                bat '"C:\\Python314\\python.exe" -m pytest --junitxml=test-results.xml'
            }
        }
    }

    post {
        always {
            junit allowEmptyResults: true, testResults: 'test-results.xml'
        }
    }
}
