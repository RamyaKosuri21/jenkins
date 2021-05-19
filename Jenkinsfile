pipeline {
  agent {
    node {
      label 'workstation'
}
}
  stages {

    stage('stage1') {
      steps {
        sh 'echo Hello stage1'
        }

    }
    stage('stage2') {
      steps {
          sh 'echo Hello stage2'
          }
      }

    }
    post {
      always {
         echo 'I will always say Hello again!'
           }
       }

}