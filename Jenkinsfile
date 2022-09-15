node {
  stage('SCM') {
    checkout scm
  }/*a*/
  stage('SonarQube Analysis') {
    def mvn = tool '3.8.2';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=sonar.source.support:missing-import"
    }
  }
}
