pipeline{
   agent any
   stages{ 
      stage('build image') {
         steps{
            docker-compose build

	stage('docker-compose up') {		
	 steps {
		docker-compose up -d
	      }	
           }
         }
      }
   }
}

