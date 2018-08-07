pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building....'
                sh "gem install bundler"
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                sh "bundle exec rake db:create"
                sh "bundle exec rake db:migrate"
                sh "bundle exec rspec spec"
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