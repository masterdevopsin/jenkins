pipeline {
    // agent any

    options {
        disableConcurrentBuilds(abortPrevious: true)
    }

    environment {
        APP_DIR = "calculator_app"
    }

    stages {
        stage ('CLONE') {
            steps {
            git branch: 'main', url: 'https://github.com/masterdevopsin/java_app.git'
            }
        }

        stage ('VALIDATE') {
            steps {
                dir("${APP_DIR}"){
                    sh ' mvn validate'
                }
            }
        }
        stage ('COMPILE') {
            steps {
                 dir("${APP_DIR}"){
                    sh ' mvn compile'
                }
            }
        }
        stage ('TEST') {
            steps {
                 dir("${APP_DIR}"){
                    sh ' mvn test'
                }
                junit '**/target/surefire-reports/*.xml' 
            }
        }
        // stage ('SONARQUBE ANALYSIS') {
        //     steps {
        //         catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
        //           timeout(time: 1, unit: 'MINUTES') {
        //              withSonarQubeEnv('SonarQube') {
        //                 dir("${APP_DIR}") {
        //                     sh 'mvn sonar:sonar'
        //                  }
        //               }
        //           }
        //         }
        //     }
        // }
        stage ('PACKAGE') {
            steps {
                 dir("${APP_DIR}"){
                    sh ' mvn package'
                }
            }
        }
    }
}