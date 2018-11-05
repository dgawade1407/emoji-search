pipeline{
  agent {
        node{
            label 'master'
        }
    } 
    stages {
	
	stage("checkout") {
           steps {
		script{
			//friendly_shockley is docker container name
			 sh """docker exec friendly_shockley git pull origin master"""
		      }
				
                 }
	}
		
     }
}
