pipeline {
  agent {
    node {
      label 'workstation'
}
}
  options {
  disableConcurrentBuilds()
  buildDiscarder(logRotator(numToKeepStr: '1'))
  }
  parameters {
    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

    booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

    choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
      }
  tools{
    nodejs 'node'
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