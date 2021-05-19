pipeline {
  agent {
    node {
      label 'workstation'
}
}
  environment{
    SURL = "pipeline.google.com"
    CREDS = credentials('CENTOS')
  }
  stages {

    stage('stage1') {
      environment{
    SURL= "stage.google.com"
    }
      steps {
        sh 'echo Hello stage1, URL = ${SURL}, CREDS =${CREDS}'

        }

    }
    stage('stage2') {
      steps {
          sh 'echo Hello stage2, URL = ${SURL}'
          }
      }

    }
    post {
      always {
         echo 'I will always say Hello again!'
           }
       }

}