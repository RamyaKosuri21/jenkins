// pipeline {
//   agent {
//     node {
//       label 'workstation'
// }
// }
//   options {
//   disableConcurrentBuilds()
//   buildDiscarder(logRotator(numToKeepStr: '1'))
//   }
//   parameters {
//     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//
//     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//
//     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//
//     choice(name: 'ENV', choices: ['dev', 'qa', 'prod'], description: 'Pick env')
//
//     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//       }
//   tools{
//     nodejs 'node'
//   }
//   environment{
//     SURL = "pipeline.google.com"
//     CREDS = credentials('CENTOS')
//   }
//   stages {
//
//     stage('stage1') {
//       when {
//         beforeAgent true
//         beforeInput true
//         anyOf{
//           environment name: 'ENV', value: 'qa'
//           environment name: 'ENV', value: 'dev'
//         }
//       }
//       input{
//         message "Should we continue?"
//         ok "Yes, we should."
//       }
//       environment{
//        SURL= "stage.google.com"
//       }
//       steps {
//         sh 'echo Hello stage1, URL = ${SURL}, CREDS =${CREDS}'
//         sh 'npm install'
//       }
//
//     }
//     stage('stage2') {
//       when {
//           environment name: 'ENV', value: 'prod'
//         }
//       steps {
//           sh 'echo Hello stage2, URL = ${SURL}'
//       }
//     }
//
//     stage('Parallel Stages'){
//       parallel{
//
//          stage('sleep-30'){
//            steps{
//              sh 'sleep 30'
//            }
//          }
//
//          stage('sleep-60'){
//            steps {
//              sh 'sleep 60'
//            }
//          }
//       }
//     }
//   }
//
//  post {
//    always {
//      echo 'I will always say Hello again!'
//    }
//
//  }
//
// }


pipeline {
    agent none
    stages {
        stage('BuildAndTest') {
            matrix {
                agent any{
                axes {
                    axis {
                        name 'PLATFORM'
                        values 'linux', 'windows', 'mac'
                    }
//                     axis {
//                         name 'BROWSER'
//                         values 'firefox', 'chrome', 'safari', 'edge'
//                     }
                }
                stages {
                    stage('Build') {
                        steps {
                            echo "Do Build for ${PLATFORM}"

                        }
                    }
                }
            }
        }
    }
}