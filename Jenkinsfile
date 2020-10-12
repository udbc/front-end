pipeline {
  agent none
  stages {
    stage('build') {
      agent {
        docker {
          image 'node:4-alpine'
        }

      }
      steps {
        sh 'npm install'
      }
    }

    stage('test') {
      agent {
        docker {
          image 'node:4-alpine'
        }

      }
      steps {
        sh 'npm install'
        sh 'npm test'
      }
    }

    stage('package') {
      agent {
        node {
          label 'node:4-alpine'
        }

      }
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