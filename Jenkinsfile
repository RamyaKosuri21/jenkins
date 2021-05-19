pipeline {
  agent {
    node {
      label 'workstation'
}
}
  stages {

    stage('sample') {
      steps {
        sh 'echo Hello stage1'
        }

    }
    stage('sample') {
      steps {
          sh 'echo Hello stage2'
          }
      }

    }
}