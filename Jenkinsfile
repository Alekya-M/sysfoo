pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'compiling....'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'running UTs....'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'generating artifacts....'
        sh 'mvn package -DskipTests'
      }
    }

    stage('post-test') {
      steps {
        echo 'post packaging'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
}