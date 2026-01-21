pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/namita1408/jenkins.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-python-app .'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'docker run --rm my-python-app pytest'
            }
        }

        stage('Run Application') {
            steps {
                bat 'docker run --rm my-python-app python app.py'
            }
        }
    }
}
