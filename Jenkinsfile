 pipeline {
  agent any
  
  environment {
    DOCKER_IMAGE = 'shahharshil/pipeline:latest'
  }
  
  stages {
    stage('Build') {
      steps {
        script {
          docker.build(DOCKER_IMAGE)
        }
      }
    }
    
    stage('Push') {
      steps {
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
          sh "docker pull ${DOCKER_IMAGE}"
          sh "docker run -d -p 8085:80 ${DOCKER_IMAGE}"
        }
      }
    }
  }
}

