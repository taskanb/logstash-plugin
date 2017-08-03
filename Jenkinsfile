pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /home/bitwiseman/docker/.m2:/root/.m2'
    }
  }
  stages {
    stage('Build') {
      steps {
        sh './tools/build.sh'
      }
    }
    stage('Test') {
      steps {
        sh './tools/test.sh'
      }
    }
  }
}
