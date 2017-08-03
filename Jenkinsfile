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
        sh 'mvn -B -DskipTests clean install'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn -B test'
      }
    }
  }
}
