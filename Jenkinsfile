pipeline {
    agent any

    environment{
        CURRENT_ENV = 'prod'
    }

    parameters {
                    booleanParam(name: 'DEPLOY', defaultValue: '', description: 'to deploy directly ')
                }

    stages {
        stage('stage 1 when branch') {
            when {
                branch 'main'  
            }
            steps {
                    echo "this is when for branch"
                    sh '''
                        sleep 5
                        exit 1
                    '''
            }
        }

        

        stage('When environment') {
            when {
                environment name: CURRENT_ENV, value: 'prod'
            }
            steps {
                echo "this is when for env"
                sh 'sleep 5'
            }
        }

        stage('When parameter') {
            when {
                expression  {param.DEPLOY == true}
            }
            steps {
                echo "this is when for env"
                sh 'sleep 5'
            }
        }

        stage('When parameter and branch ') {
            when {
                allof{
                    branch 'main'
                    expression  {param.DEPLOY == true}
                }
            }
            steps {
                echo "this is when for env"
                sh 'sleep 5'
            }
        }

        stage('When parameter or branch ') {
            when {
                anyof{
                    branch 'main'
                    expression  {param.DEPLOY == true}
                }
            }
            steps {
                echo "this is when for env"
                sh 'sleep 5'
            }
        }

        stage('not parameter and branch ') {
            when {
                not{
                    branch 'main'
                    expression  {param.DEPLOY == true}
                }
            }
            steps {
                echo "this is when for env"
                sh 'sleep 5'
            }
        }



    }
} 