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

    stage ('Deploy Stage') {
   
   
	   steps{
            withMaven(maven: 'Local Maven') {
            sh 'mvn deploy'
          }
      }
  }

}	
	
}
