pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region: 'eu-west-2', credentials: 'aws-static') {
          s3Upload(file: 'index.html', bucket: 'devops-nd-ci-cd-project', path: '/')
        }
      }
    }
  }
}