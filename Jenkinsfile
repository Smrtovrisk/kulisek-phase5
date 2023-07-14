pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-react-app .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop my-react-app || true && docker rm my-react-app || true'
                sh 'docker run -d -p 80:80 --name my-react-app my-react-app'
            }
        }
    }
}
