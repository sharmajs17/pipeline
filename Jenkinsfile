 pipeline {
        agent {
            docker-compose { image 'myimage' }
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
                    sh 'echo not yet...'
                }
            }
        }
    }
