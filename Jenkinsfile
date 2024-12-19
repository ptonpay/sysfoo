pipeline {
   agent  any
   triggers { pollSCM( 'H/2 * * * *' ) }

   tools {
     maven 'maven 3.9.9'
   }
  
  stages{
       stage("Build"){
           steps{
              echo 'step 1 Building'
              sh 'mvn compile' 
           }
       }
       stage("Test"){
           steps{
               echo 'step 2 Testing'
               sh 'mvn clean test'
           }
       }
       stage("Package"){
           steps{
               echo 'step 3 Packaging'
               sh 'mvn package -DskipTests' 
            }
       } 
   }
   post{
     always{
         echo 'This pipeline is completed..'
     }
   } 
}
