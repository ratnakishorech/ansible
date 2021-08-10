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
            sonar.projectKey=python-project-test2
            sonar.projectName=python-project-test2
            sonar.projectVersion=1.0
            sonar.sources=.
            sonar.language=py
            sonar.sourceEncoding=UTF-8
            # Test Results
            sonar.python.xunit.reportPath=nosetests.xml
            # Coverage
            sonar.python.coverage.reportPath=coverage.xml
            # Linter (https://docs.sonarqube.org/display/PLUG/Pylint+Report)
            #sonar.python.pylint=/usr/local/bin/pylint
            #sonar.python.pylint_config=.pylintrc
            #sonar.python.pylint.reportPath=pylint-report.txt
           -Dsonar.host.url=http://34.234.40.43:9000/ \
           -Dsonar.login=72493430aec029262973c8bad4aa0178c5162c09"
           }
       }
   }
   stage("Install Project Dependencies") {
   steps {
       //nodejs(nodeJSInstallationName: 'nodenv'){
           sh "npm install"
       }//
   }
}
}
