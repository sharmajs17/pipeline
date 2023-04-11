pipeline {
  agent any
  
  environment {
    DOCKERHUB_CREDENTIALS= credentials('docker')
    }
  }  
  stages {
    stage('Build') {
      steps {
	sh 'docker build -t myimage:latest .'
      }
    }
    
    stage('tag') {
      steps {
	sh 'docker tag myimage:latest shahharshil/myimage'
        }
      }
    stage('push') {
      steps {
	sh 'docker push shahharshil/myimage'
    }
  }
}
