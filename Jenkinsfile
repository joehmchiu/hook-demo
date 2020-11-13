pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Hi, GeekFlare. Starting to build the App.'
      }
    }
    stage('Test') {
      steps {
        echo "testing..."
        sh "ls -lRrth"
      }
    }
    stage('Deploy') {
      parallel {
        stage('Deploy start ') {
          steps {
            echo "Start the deploy .."
          }
        }
      }
    }
    stage('Prod') {
      steps {
        echo "App is Prod Ready"
      }
    }
  }
}
