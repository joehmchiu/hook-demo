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
            assert props['attr1'] == 'One'
            assert props.attr1 == 'One'

            def props = readJSON text: '{ "key": "value" }'
            assert props['key'] == 'value'
            assert props.key == 'value'

            def props = readJSON text: '[ "a", "b"]'
            assert props[0] == 'a'
            assert props[1] == 'b'

            def props = readJSON text: '{ "key": null, "a": "b" }', returnPojo: true
            assert props['key'] == null
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
