try {
stage("Building SONAR ...") {
sh './gradlew clean sonarqube'
}
} catch (e) {emailext attachLog: true, body: 'See attached log', subject: 'BUSINESS Build Failure', to: 'abc@gmail.com'
step([$class: 'WsCleanup'])
return
}
sonarqube {
properties {
property "sonar.host.url", http://34.234.40.43:9000/ //  url is your sonar server
property "sonar.projectName", "python-project-test2"   //  this name will appear in dashboard
property "sonar.projectKey", "python-project-test2" // It sould be a keybased on this report is created
property "sonar.groovy.jacoco.reportPath", "${project.buildDir}/jacoco/test.exec"    }
}
