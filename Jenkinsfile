pipeline {
  agent any
  
  environment {
    DOCKERHUB_CREDENTIALS= credentials('pipeline')
  }
  
  stages {
    stage('Build') {
      steps {
	sh 'docker build -t myimage:latest .'
        script {	
          docker.build(myimage:latest)
        }
      }
    }
    
    stage('Push') {
      steps {
	sh 'docker tag myimage:latest shahharshil/myimage'
            dockerImage.push()
          }
        }
      }
    stage('Deploy') {
      steps {
	sh 'docker push shahharshil/myimage'
        script {
        }
      }
    }
  }



