pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm install'
            }
            }

        stage('Test') {
            steps {
                echo 'Testing'
                sh 'npm test'
            }
        }
        stage('Packaging') {
            steps {
                echo 'Packaging....'
                sh 'npm run package'
            }
        }
    }
    
    post{
       always{
           echo 'this pipeline has completed'
}
}
}
