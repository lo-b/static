pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      sh 'tidy -q -e *.html'
    }
    stage('Upload to AWS') {
      steps {
        withAWS(region: 'eu-west-2', credentials: 'aws-static') {
          s3Upload(pathStyleAccessEnabled: true, 
            payloadSigningEnabled: true, 
            file:'index.html', 
            bucket:'devops-nd-ci-cd-project'
          )
        }
      }
    }
  }
}