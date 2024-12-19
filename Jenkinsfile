pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'step 1 Building'
        sh 'mvn compile'
      }
    }

    stage('Test') {
      steps {
        echo 'step 2 Testing'
        sh 'mvn clean test'
      }
    }

    stage('Package') {
      steps {
        echo 'step 3 Packaging'
        sh 'mvn package -DskipTests'
        sh 'sh \'echo hi Pranay\''
      }
    }

  }
  tools {
    maven 'maven 3.6.1'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
  triggers {
    pollSCM('H/2 * * * *')
  }
}