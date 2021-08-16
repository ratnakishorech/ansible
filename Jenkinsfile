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
       def scannerHome = tool 'SonarQube Scanner ';
           //withSonarQubeEnv("sonarqube-container") {
           sh "${tool("SonarQube Scanner")}/bin/sonar-scanner \
           -Dsonar.projectKey=python-project-test2 \
           -Dsonar.sources=. \
           -Dsonar.css.node=. \
           -Dsonar.host.url=http://34.234.40.43:9000/ \
           -Dsonar.login=72493430aec029262973c8bad4aa0178c5162c09"
               }
           }
       }
   }
   stage("Install Project Dependencies") {
   steps {
       //nodejs(nodeJSInstallationName: 'nodenv'){
           sh "npm install"
           }
       }
   }
}
}
