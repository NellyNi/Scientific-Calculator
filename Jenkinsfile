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
mvn sonar:sonar -Dsonar.projectKey=io.michaelcane:bestcalculator -Dsonar.host.url=http://localhost:9000 -Dsonar.login=42b26f3c31091ce7781e7a608d318c0ef649dc2c'''
      }
    }

  }
}