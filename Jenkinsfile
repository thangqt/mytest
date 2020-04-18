pipeline {

agent {
    docker {
        image 'maven:3.6.3-ibmjava-8-alpine'
        args '-v $HOME/.m2:/root/.m2'
           }
   stages {
      stage('checkout') {
         steps {
            git 'https://github.com/effectivejenkins/spring-petclinic.git'
         }
      }
   
      stage('Build') {
         steps {
	    sh 'mvn --version'
            sh 'mvn clean package'
            junit '**/target/surefire-reports/TEST-*.xml'
         }
      }
   }
}
