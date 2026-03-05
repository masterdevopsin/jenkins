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
                                #!/bin/bash
                                pwd
                                ls -lrt
                                sleep 5
                            '''
                        }
                    }
                }

        }