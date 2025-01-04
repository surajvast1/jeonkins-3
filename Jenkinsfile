pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Installing dependencies...'
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './venv/bin/python -m unittest discover -s .'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'mkdir -p /tmp/deployment'
                sh 'cp app.py /tmp/deployment/'
            }
        }
    }
}
