pipeline {
  agent any 
  stages {
    stage('Build') {
      steps {
        bat './tools/build.sh'
      }
      post {
        success {
          archiveArtifacts 'target/*.hpi,target/*.jpi'   
        }
        
      }
    }
    stage('Test') {
      steps {
        bat './tools/test.sh'
      }
      post {
        always {
          junit '**/surefire-reports/**/*.xml'
          
        }
        
      }
    }
  }
}