pipeline {
    agent any

    options {
        disableConcurrentBuilds(abortPrevious: true)
    }

    environment {
        APP_DIR = "calculator_app"
    }

    stages {
        stage ('CLONE'){
            steps {
            git branch: 'main', url: 'https://github.com/masterdevopsin/java_app.git'
            }
        }

        stage (' VALIDATE'){
            steps {
                dir("${APP_DIR}"){
                    echo "${APP_DIR}"
                    sh ' mvn validate'
                    echo "validate success"
                }
            }
        }
        stage (' COMPILE') {
            steps {
                 dir("${APP_DIR}"){
                    echo "${APP_DIR}"
                    sh ' mvn compile'
                    echo "compile success"
                }
            }
        }
    }
}