        pipeline  {
                agent { label 'slave-2 && slave-3' }
                stages {
                    stage('stage 1') {
                        steps {
                            sh 'sleep 5'
                            echo "this is stage 1"
                        }
                    }
                    stage('stage 2') {
                        steps {
                            sh '''
                               pipeline  {
                agent { label 'slave-1' }

                environment {
                    DOCKER_USERNAME = 'sree'
                    AWS_ACCESS_KEY = '1234567890'
                }
                stages {
                    stage('stage 1') {
                        steps {
                         echo "DOCKER_USERNAME: ${DOCKER_USERNAME}"
                         echo "AWS_ACCESS_KEY: ${AWS_ACCESS_KEY}"
                         
                         
                         sh'''
                           env
                         '''

                        }
                    }
                    
                }

        }         #!/bin/bash
                                pwd
                                ls -lrt
                                sleep 5
                            '''
                        }
                    }
                }

        }