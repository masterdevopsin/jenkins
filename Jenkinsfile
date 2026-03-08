
        pipeline  {
                agent any

                environment {
                    DOCKER_USERNAME = 'sree'
                    AWS_ACCESS_KEY = '1234567890'
                }
                stages {
                    stage('stage 1') {
                        steps {
                        catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE'){
                         echo "this is stage1 "
                          sh '''
                            sleep 5
                            exit 1
                          '''
                        }
                        }
                    }
                    stage('PARALLEL ') {
                        parallel{
                            stage ('WINDOWS TEST '){
                                steps {
                                echo "this is windows "
                                sh ' sleep 5'
                                }
                            }
                            stage ('MAC TEST '){
                                steps {
                                echo "this is mac "
                                sh ' sleep 5'
                                }
                            }
                            stage ('LINUX TEST '){
                                steps {
                                echo "this is linux "
                                sh ' sleep 5'
                                }
                            }
                         }
                    }
                    stage('Final') {
                        steps {
                         echo "this is final stage "
                          sh 'sleep 5'
                        }
                    }
                    
                }

        }