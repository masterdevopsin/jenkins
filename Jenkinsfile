pipeline {
    agent any

    stages {

        stage('Build - Dev') {
            when {
                branch 'dev'
            }
            steps {
                echo "Running DEV build"
            }
        }

        stage('Test - QA') {
            when {
                branch 'qa'
            }
            steps {
                echo "Running QA tests"
            }
        }

        stage('Deploy - Main') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying to Production"
            }
        }

    }
}
