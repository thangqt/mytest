pipeline {
   agent {
        docker {
            image 'maven:3.6.3-ibmjava-8-alpine'
            args '-u root'
        }
    }
   stages {
      stage('checkout') {
         steps {
            git 'https://github.com/effectivejenkins/spring-petclinic.git'
         }
      }
   
      stage('Build') {
         steps {
            sh 'mvn clean  package'
            junit '**/target/surefire-reports/TEST-*.xml'
         }
      }
   }
}
