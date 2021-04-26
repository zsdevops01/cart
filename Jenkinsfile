@Library('roboshop') _

pipeline {
  agent {
    label 'NODEJS'
  }

  stages {

    stage('Download Dependencies') {
      steps {
        sh '''
          npm install
        '''
      }
    }

    stage('Prepare Artifacts') {
      steps {
        sh '''
          zip -r cart.zip node_modules server.js
        '''
      }
    }

    stage('Upload Artifacts') {
      steps {
       script {
         nexus
       }
      }
    }

  }

}