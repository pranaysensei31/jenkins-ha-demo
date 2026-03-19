pipeline {
    agent any

    triggers {
        cron('H/5 * * * *')
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello from Jenkins HA Pipeline!'
            }
        }

        stage('Check Node') {
            steps {
                echo "Running on: ${env.NODE_NAME}"
                echo "Job: ${env.JOB_NAME}"
                echo "Build #: ${env.BUILD_NUMBER}"
            }
        }

        stage('Simulate Build') {
            steps {
                echo 'Simulating build process...'
                sh 'echo Build started at $(date)'
                sh 'sleep 2'
                echo 'Build complete!'
            }
        }

        stage('Simulate Test') {
            steps {
                echo 'Running tests...'
                sh 'echo All tests passed!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline ran successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
