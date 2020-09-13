pipeline {
   
   agent any
   
   tools{
     NodesJS 'NodesJS 4.8.6'
   }
   
   stages{

    stage('build'){
      steps{
        sh 'npm install'
      }
    }

    stage('test'){
      steps{
        sh 'npm install'
        sh 'npm test'
      }
    }	

    stage('package'){
      steps{
        sh 'npm install'
        sh 'npm run package'
      }
    }
   }
}
