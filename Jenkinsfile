pipeline {
agent any
//tools {nodejs "nodenv"}
stages {
 stage("Code Checkout from Github") {
  steps {
   git branch: 'devel',
    credentialsId: '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',
    url: 'https://github.com/ratnakishorech/ansible.git'
  }
 }
   stage('Code Quality Check via SonarQube') {
   steps {
       script {
       def scannerHome = tool 'SonarQube Scanner 4.6.2.2472';
           //withSonarQubeEnv("sonarqube-container") {
           sh "${tool("SonarQube Scanner 4.6.2.2472")}/bin/sonar-scanner \
           -Dsonar.projectKey=python-project-test2\
           -Dsonar.sources=. \
           -Dsonar.css.node=. \
           -Dsonar.host.url=http://65.1.48.84:9000/ \
           -Dsonar.login=7c4caab7e457ab7ac317f8dec0d5634ff72aa58c"
           }
       }
   }
}
}
