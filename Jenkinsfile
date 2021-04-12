pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''git pull
cd Calculator/
mvn install'''
      }
    }

    stage('test') {
      steps {
        sh '''cd Calculator/
mvn -Dtest=CalculatorSpec test'''
      }
    }

    stage('static analyst') {
      steps {
        sh '''cd Calculator/
mvn sonar:sonar -Dsonar.projectKey=io.michaelcane:bestcalculator -Dsonar.host.url=http://localhost:9000 -Dsonar.login=6a329fdfa7aba58520fc20a9fa83148fa40cceb5'''
      }
    }

  }
}