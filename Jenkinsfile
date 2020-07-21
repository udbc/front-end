pipeline {
    agent any

    // tools {
    //   node 'v4.8.6'
    // }

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
                archiveArtifacts artifacts: 'distribution/*.zip', fingerprint: true
            }
        }
    }
}