pipeline {
    agent {
        docker { 
            image 'docker:latest'
            reuseNode true
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-app .' //  'cd /app' больше не нужен, так как мы внутри контейнера docker
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop my-app || true && docker rm my-app || true && docker run -d -p 8000:8000 --name my-app my-app'
            }
        }
    }
}
