pipeline {
    agent any

    options {
        disableConcurrentBuilds(abortPrevious: true)
    }

    stages {
        stage ('CLONE'){
            steps {
            git branch: 'main', url: 'https://github.com/masterdevopsin/java_app.git'
            }
        }

        stage (' VALIDATE'){
            steps {
                sh 'mvn validate'
                echo "validate success"
            }
        }
    }
}