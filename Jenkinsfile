 pipeline {
        agent {
            docker { image 'shahharshil/python1' } 
        }
        stages {
            stage('Build') {
                steps {
                    sh 'docker-compose build nginx django_gunicorn'
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
