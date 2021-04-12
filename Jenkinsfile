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
mvn sonar:sonar -Dsonar.projectKey=io.michaelcane:bestcalculator -Dsonar.host.url=http://localhost:9000 -Dsonar.login=b21eb28d25c7933042aa91a8982149b7516394ca'''
      }
    }

  }
}