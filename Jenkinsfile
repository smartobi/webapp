pipeline {
    
    agent any
    stages {
       stage ('Check-Git-Secrets') {
       steps {
        sh 'rm trufflehog || true'
        sh 'docker run -t gesellix/trufflehog --json https://github.com/smartobi/webapp.git > trufflehog'
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
