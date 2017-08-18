pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        sh './tools/build.sh'
      }
      post {
        success {
          archiveArtifacts 'target/*.hpi,target/*.jpi'
          
        }
        
      }
    }
    stage('Test') {
      steps {
        sh './tools/test.sh'
      }
      post {
        always {
          junit '**/surefire-reports/**/*.xml'
          
        }
        
      }
    }
  }
}