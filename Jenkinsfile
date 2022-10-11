pipeline {
//Just for Test
  agent any
  stages {
    stage ('Build'){ //feature/* develop main
      steps {
        sh './gradlew build'
      }
    }
    stage ('Test'){ //develop main
      when {
        anyOf { //only develop and main branch
          branch 'develop';
          branch 'main'
        }
      }
      steps {
        sh './gradlew test'
      }
    }
    stage ('Deploy'){ // main
      when { //only main branch
        branch 'main'
      }
      steps {
        echo "Deploy"
      }
    }
  }
}
