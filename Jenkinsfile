 pipeline {
        agent {
            docker { image 'shahharshil/python1' , 'shahharshil/python2' } 
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
