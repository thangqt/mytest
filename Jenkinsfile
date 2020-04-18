pipeline {
   agent { docker 'maven:3.6.3-ibmjava-8-alpine' }
   stages {
      stage('checkout') {
         steps {
            git 'https://github.com/effectivejenkins/spring-petclinic.git'
         }
      }
   
      stage('Build') {
         steps {
            sh 'mvn clean package'
            junit '**/target/surefire-reports/TEST-*.xml'
         }
      }
   }
}
