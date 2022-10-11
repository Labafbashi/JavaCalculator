pipeline {
  agent any
  stages {
    stage ('Build'){ //feature/* develop main
      steps {
        sh './gradlew build'
      }
    }
    stage ('Test'){ //develop main
      when {
        anyOf {
          branch 'develop';
          branch 'main'
        }
      }
      steps {
        sh './gradlew test'
      }
    }
    stage ('Deploy'){ // main
      when {
        branch 'main'
      }
      steps {
        echo "Deploy"
      }
    }
  }
}
