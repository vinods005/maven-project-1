pipeline{
  agent any
    
	
  stages 
  {
  
    stage ('SCM checkout') {
       git 'https://github.com/vinods005/maven-project-1.git'
      }
   }

   { 

   
   stage ('Testing Stage') {
   
   
	steps{
          withMaven(maven: 'Local Maven') {
          sh 'mvn install'
          }
      }
  }
}

   {
	   
   stage ('deploy to tomcat'){


        steps {
           sshagent(['18.197.155.60']) {
           sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@52.59.247.170:/var/lib/tomcat/webapps/'
      }
   }
}	
}	   	   
}
