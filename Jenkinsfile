pipeline {
  agent {
    docker {
      image 'schoolofdevops/node:4-alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        echo 'Building...'
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing...'
        sh 'npm install'
        sh 'npm test'
      }
    }

    stage('Package') {
      steps {
        echo 'Packaging....'
        sh 'npm install'
        sh 'npm run package'
        archiveArtifacts(artifacts: 'distribution/*.zip', fingerprint: true)
      }
    }

  }
}