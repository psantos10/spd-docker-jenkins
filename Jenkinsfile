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
        stage('Deploy') {
            steps {
                step {
                    echo 'START Deploying....' 
                }
                
                step {
                    if (env.BRANCH_NAME == 'preview') {
                        echo 'Deploying to staging/preview environment'
                    }

                    if (env.BRANCH_NAME == 'master') {
                        echo 'Deploying to production environment'
                    }
                }

                step {
                    echo 'FINISH Deploying!' 
                }
            }
        }
    }
}