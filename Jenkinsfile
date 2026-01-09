pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-demo .'
            }
        }
        stage('Run Container') {
            steps {
                sh '''
                docker rm -f cicd-demo || true
                docker run -d -p 5000:5000 --name cicd-demo cicd-demo
                '''
            }
        }
    }
}
