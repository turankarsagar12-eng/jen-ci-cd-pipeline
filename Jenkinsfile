pipeline {
agent any

stages {
    stage('Build') {
        steps {
            sh 'docker build -t my-devops-app .'
        }
    }

    stage('Test') {
        steps {
            sh 'docker image inspect my-devops-app'
        }
    }

    stage('Deploy') {
        steps {
            sh 'docker rm -f my-devops-container || true'
            sh 'docker run -d --name my-devops-container -p 8081:80 my-devops-app'
        }
    }
}

}
