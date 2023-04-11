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
          sh "docker-compose build ${DOCKER_IMAGE}"
          sh "docker-compose up -d ${DOCKER_IMAGE}"
        }
      }
    }
  }
}

