pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-repo.git'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t employee-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8080:8080 employee-app'
            }
        }
    }
}
