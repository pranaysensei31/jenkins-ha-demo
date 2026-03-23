pipeline {
    agent any

    triggers {
        cron('* * * * *')
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning repository from GitHub...'
                sh 'sleep 3'
                echo 'Repository cloned successfully!'
            }
        }

        stage('Build') {
            steps {
                echo 'Starting build process...'
                sh 'echo Build started at $(date)'
                sh 'sleep 10'
                echo 'Compiling source code...'
                sh 'sleep 5'
                echo 'Build completed successfully!'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                sh 'sleep 5'
                echo 'Test 1 passed!'
                sh 'sleep 3'
                echo 'Test 2 passed!'
                sh 'sleep 3'
                echo 'All tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'sleep 5'
                echo 'Deployment complete!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline finished successfully on node: ${env.NODE_NAME}'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
