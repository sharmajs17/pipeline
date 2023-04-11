pipeline {   
  agent{      
    node { label 'slavefordocker'}     
  }  
  environment {     
    DOCKERHUB_CREDENTIALS= credentials('pipeline')     
  }    
  stages {         
    stage("Git Checkout"){           
      steps{                
	git credentialsId: 'github', url: 'https://github.com/Harshil-1799/pipeline.git'                 
	echo 'Git Checkout Completed'            
      }        
    }
    stage('Build Docker Image') {         
      steps{                
	sh 'sudo docker build -t myimage:latest .'           
        echo 'Build Image Completed'                
      }           
    }
    stage('Login to Docker Hub') {         
      steps{                            
	sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u shahharshil --password-Harshil@123'                 
	echo 'Login Completed'                
      }           
    }               
    stage('Push Image to Docker Hub') {         
      steps{                            
	sh 'sudo docker push myimage:latest'                 echo 'Push Image Completed'       
      }           
    }      
  } //stages 
  post{
    always {  
      sh 'docker logout'           
    }      
  }  
} //pipeline
