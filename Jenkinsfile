 pipeline {
  agent any
  
  environment {
    DOCKERHUB_CREDENTIALS= credentials = 'pipeline'
  }
  
  stages {
    stage('Build') {
      steps {
        script {
          sh "docker build -t myimage:latest ."	
          docker.build(DOCKER_IMAGE)
        }
      }
    }
    
    stage('Push') {
      steps {
          sh "docker tag myimage:latest shahharshil/myimage:latest"
        script {
          docker.withRegistry('shahharshil/pipeline:latest', 'pipeline') {
            dockerImage.push()
          }
        }
      }
    }
    
    stage('Deploy') {
      steps {
        script {
          sh "docker push shahharshil/myimage:latest"
        }
      }
    }
  }
}

