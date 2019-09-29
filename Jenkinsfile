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

}
