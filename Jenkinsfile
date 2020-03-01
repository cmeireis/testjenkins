pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'tidy -q -e index.html'
      }
    }

    stage('Upload to AWS') {
      steps {
        s3Upload(bucket: 'cmdeploywebinfra', pathStyleAccessEnabled: true, payloadSigningEnabled: true, file: 'index.html')
      }
    }

  }
}