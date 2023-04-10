 pipeline {
        agent {
            docker { image 'shahharshil/myimage' 'shahharshil/python' } 
        }
        stages {
            stage('Build') {
                steps {
                    sh 'docker-compose build'
                }
            }

            stage('Test') {
                steps {
                    sh 'docker-compose up -d'
                }
            }

            stage('Deploy') {
                steps {
                    sh 'docker ps'
                }
            }
        }
    }
