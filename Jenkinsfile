pipeline {
    agent any

    stages {
        stage('Pull') {
            steps {
                sh 'docker pull smrtovrisk/kulisek-phase5-docker-image:1.0'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop kulisek-phase5-container || true && docker rm kulisek-phase5-container || true'
                sh 'docker run -d -p 80:80 --name kulisek-phase5-container smrtovrisk/kulisek-phase5-docker-image:1.0'
            }
        }
    }
}
