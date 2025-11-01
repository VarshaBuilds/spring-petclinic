pipeline {
  agent any
  tools {
    maven 'maven3'
    jdk 'jdk21'
  }
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/spring-projects/spring-petclinic.git'
      }
    }
    stage('Build') {
      steps {
        bat 'mvn clean package -DskipTests'
      }
    }
    stage('Test') {
      steps {
        bat 'mvn test'
      }
    }
  }
  post {
    success {
      echo 'Jenkinsfile pipeline executed successfully!'
    }
    failure {
      echo 'Something went wrong in the Jenkinsfile pipeline!'
    }
  }
}
