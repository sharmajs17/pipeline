 pipeline {
  agent any
  
  environment {
    DOCKER_IMAGE = 'shahharshil/python2'
  }
  
  stages {
    stage('Build') {
      steps {
        script {
          docker.build shahharshil/python2
        }
      }
    }
    
    stage('Push') {
      steps {
        script {
          docker.withRegistry('shahharshil/python2', 'pipeline') {
            dockerImage.push()
          }
        }
      }
    }
    
    stage('Deploy') {
      steps {
        script {
          sh "docker pull ${shahharshil/python2}"
          sh "docker run -d -p 8085:80 ${shahharshil/python2}"
        }
      }
    }
  }
}

