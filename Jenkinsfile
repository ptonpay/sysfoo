pipeline {
   agent  any
   triggers { pollSCM( 'H/2 * * * *' ) }

   tools {
     maven 'Maven 3.6.1'
   }
  
  stages{
       stage("Build"){
           steps{
              echo 'step 1 Building'
              mvn compile 
           }
       }
       stage("Test"){
           steps{
               echo 'step 2 Testing'
               mvn clean test
           }
       }
       stage("Package"){
           steps{
               echo 'step 3 Packaging'
               mvn package -DskipTests 
           }
    } }
   post{
     always{
         echo 'This pipeline is completed..'
     }
} }