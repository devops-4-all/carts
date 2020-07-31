pipeline {
  agent {
    docker {
      image 'schoolofdevops/carts-maven'
    }

  }
  stages {
    stage('Build') {
      steps {
        echo 'Building...'
        sh 'mvn clean compile'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing...'
        sh 'mvn clean test'
      }
    }

    stage('Package') {
      steps {
        echo 'Packaging....'
        sh 'mvn package -DskipTests '
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
}