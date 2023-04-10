pipeline {
    agent docker
    stages {
        stage('build') {
            agent {
                docker { image 'shahharshil/python1' }
            }
            steps {
                sh 'docker-compose build'
            }
        }
        stage('build') {
            agent {
                docker { image 'shahharshil/python2' }
            }
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
