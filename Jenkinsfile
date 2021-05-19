pipeline {
  agent {
    node {
      label 'workstation'
}
}
  environment{
    URL = "pipeline.google.com"
  }
  stages {

    stage('stage1') {
      environment{
    URL= "stage.google.com"
    }
      steps {
        sh 'echo Hello stage1, URL = ${URL}'
        }

    }
    stage('stage2') {
      steps {
          sh 'echo Hello stage2, URL = ${URL}'
          }
      }

    }
    post {
      always {
         echo 'I will always say Hello again!'
           }
       }

}