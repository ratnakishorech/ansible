try {
stage("Building SONAR ...") {
sh './gradlew clean sonarqube'
} 
stage("pushing code to sonarqube"){
sonarqube {
properties {
property "sonar.host.url", http://34.234.40.43:9000/ 
property "sonar.projectName", "python-project-test2"   
property "sonar.projectKey", "python-project-test2"
property "sonar.groovy.jacoco.reportPath", "${project.buildDir}/jacoco/test.exec"    }
}
}
}
