pipeline{
  agent any
    
	
  stages 
  {
  
    stage ('SCM checkout') {
       git 'https://github.com/vinods005/jenkins_pipeline_hello.git'
      }
   }

   { 

   
   stage ('Testing Stage') {
   
   
	steps{
          withMaven(maven: 'Local Maven') {
          sh 'mvn test'
          }
      }
  }
}

   stage ('deploy to tomcat'){


        steps {
           sshagent(['18.185.108.214']) {
           sh 'scp -o StrictHostKeyChecking=no **/*.war ec2-user@18.185.108.214:/var/lib/tomcat/webapps'
      }
   }
}	

}
