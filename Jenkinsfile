pipeline {
    agent any

    stages {

      stage('CHECKOUT') {
    steps {
        checkout([$class: 'GitSCM',
            branches: [[name: '*/main']],
            extensions: [],
            userRemoteConfigs: [[
                credentialsId: 'jenkins-git',
                url: 'https://github.com/masterdevopsin/jenkins.git'
            ]]
        ])
    }
}

        stage('stage 1 when branch') {
            when {
                branch 'main'
            }
            steps {
                echo "this is when for branch"
                sh '''
                sleep 5
                '''
            }
        }

        stage('When parameter and branch') {
            when {
                allOf {
                    branch 'main'
                    expression { params.DEPLOY == true }
                }
            }
            steps {
                echo "branch AND parameter true"
                sh 'sleep 5'
            }
        }

        stage('When parameter or branch') {
            when {
                anyOf {
                    branch 'main'
                    expression { params.DEPLOY == true }
                }
            }
            steps {
                echo "branch OR parameter"
                sh 'sleep 5'
            }
        }

        stage('Not main branch') {
            when {
                not {
                    branch 'main'
                }
            }
            steps {
                echo "this runs when branch is NOT main"
                sh 'sleep 5'
            }
        }

    }
}