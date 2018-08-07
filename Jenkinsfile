pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        
        stage('Deploy to PREVIEW') {
            when {
                branch 'develop'
            }

            steps {
                echo 'Deploying to PREVIEW'
            }
        }

        stage('Deploy to PRODUCTION') {
            when {
                branch 'master'
            }

            steps {
                echo 'Deploying to PRODUCTION'
            }
        }
    }
}