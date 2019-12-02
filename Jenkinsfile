pipeline {
    agent any
    stages {

    stage('Build') {
           steps {
            dir ('simple-java-maven-app') {
                 
                sh 'mvn clean package'
            }   
        } 
       
   }
   stage('Archive') {
         steps {
           dir ('simple-java-maven-app/target') {
           archive '*.jar'
         }  
      } 
      
   }  
    }
    post {
        always {
            echo 'I have finished and deleting workspace'
            deleteDir() 
        }
        success {
            echo 'Job succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}