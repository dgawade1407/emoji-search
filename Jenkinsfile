pipeline{
    agent {
        
            /*node  'master'*/
        node{
            label 'master'
        }
         /**/
           
           
        
    }

 
    /*parameters {
        //get branchName param
        string(defaultValue: 'master', description: 'get branch name from url', name: "branchname")

    }*/
    
    stages {
	

     
		stage("checkout") {
             steps {
			 
				script{
				    sh """docker exec friendly_shockley git pull origin master"""
				}
				
             }
		}
		
     }
}
