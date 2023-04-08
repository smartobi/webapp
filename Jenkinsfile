pipeline {

    agent any
    tools {
       maven 'Maven'
    }
    Stages {
     stage ('Check-Git-Secrets') {
      steps {
        sh 'rm trufflehog || true'
        sh 'docker run gesellix/trufflehog --json https://github.com/smartobi/webapp.git > trufflehog'
        sh 'cat trufflehog'
      }
    }
     stage ('Build') {
            steps {
                sh 'mvn clean package'
            }
            
        }
    }
}
