pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
          stage('SonarQube Analysis') {
      steps {
    script {
        def mvn = tool 'Default Maven'
                }
    withSonarQubeEnv(installationName: 'SonarQube') {
        script {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=opqdemo"
        }
      }
    }
  }
  }
}
