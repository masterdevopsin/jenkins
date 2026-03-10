pipeline {
    agent any

    stages {
        stage ('CLONE'){
            steps {
            git branch: 'main', url: 'https://github.com/masterdevopsin/java_app.git'
            }
        }

        stage (' VALIDATE'){
            staeps {
                sh 'mvn validate'
                echo "validate success"
            }
        }
    }
}