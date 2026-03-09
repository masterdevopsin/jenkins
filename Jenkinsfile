pipeline {
    agent any

    parameters {
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy manually')
    }



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


                echo "Current Branch: ${env.GIT_BRANCH_NAME}"
            }
        }

        stage('Stage 1 When Branch') {
            when {
                expression { env.GIT_BRANCH_NAME == 'origin/main' }
            }
            steps {
                echo "This runs when branch is main"
                sh 'sleep 5'
            }
        }

        stage('When parameter AND branch') {
            when {
                allOf {
                    expression { env.GIT_BRANCH_NAME == 'main' }
                    expression { params.DEPLOY == true }
                }
            }
            steps {
                echo "Branch main AND parameter true"
                sh 'sleep 5'
            }
        }

        stage('When parameter OR branch') {
            when {
                anyOf {
                    expression { env.GIT_BRANCH_NAME == 'main' }
                    expression { params.DEPLOY == true }
                }
            }
            steps {
                echo "Branch main OR parameter true"
                sh 'sleep 5'
            }
        }

        stage('Not main branch') {
            when {
                expression { env.GIT_BRANCH_NAME != 'main' }
            }
            steps {
                echo "This runs when branch is NOT main"
                sh 'sleep 5'
            }
        }

    }
}