pipeline {
  agent { label 'windows' }
  tools {
    maven 'mvn'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/anilkumarreddy2000/pipeline_demo_project.git'
      }
    }
    stage('Build') {
      steps {
        bat 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        bat 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        bat 'mvn package'
      }
    }
  }
}
