        pipeline  {
                agent { label 'slave-1' }

                environment {
                    DOCKER_USERNAME = 'sree'
                    AWS_ACCESS_KEY = '1234567890'
                }
                stages {
                    stage('stage 1') {
                        environment {
                            STAGE = 'stage1'
                        }
                        steps {
                         echo "DOCKER_USERNAME: ${env.DOCKER_USERNAME}"
                         echo "AWS_ACCESS_KEY: ${env.AWS_ACCESS_KEY}"
                         echo "STAGE: ${env.STAGE}"
                         
                         sh'''
                           env
                         '''

                        }
                    }
                    stage('stage 2') {
                        steps {
                         echo "DOCKER_USERNAME: ${DOCKER_USERNAME}"
                         echo "AWS_ACCESS_KEY: ${AWS_ACCESS_KEY}"
                         echo "STAGE: ${env.STAGE}"
                         
                         sh'''
                           env
                         '''

                        }
                    }
                    
                }

        }