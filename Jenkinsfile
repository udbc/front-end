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
        docker {
          image 'node:4-alpine'
        }

      }
      steps {
        sh 'npm install'
        sh 'npm run package'
        archiveArtifacts '**/distribution/*.zip'
      }
    }

    stage('docker build') {
      steps {
        script {
          docker.withRegistry('https://index.docker.io/v1/', 'dockerlogin') {
            def dockerImage = docker.build("cloudapsar/frontend:v${env.BUILD_ID}", "./")
            dockerImage.push()
            dockerImage.push("latest")
          }
        }

      }
    }

  }
  tools {
    nodejs 'NodesJS 4.8.6'
  }
}