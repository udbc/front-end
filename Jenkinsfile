pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'npm install'
      }
    }

    stage('test') {
      steps {
        sh 'npm install'
        sh 'npm test'
      }
    }

    stage('package') {
      steps {
        sh 'npm install'
        sh 'npm run package'
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'NodesJS 4.8.6'
  }
}