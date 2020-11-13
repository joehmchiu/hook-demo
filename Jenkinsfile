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
            def props = readJSON file: 'hello.json'
            props.each { key, value ->
                echo "Walked through key $key and value $value"
            }
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
