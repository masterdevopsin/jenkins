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

        }