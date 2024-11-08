pipeline {
    agent any
    
    environment {
        STAGE_3="Stage 3"
    }

    stages {
        stage('Stage 1') {
            steps {
                echo 'Stage 1'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'Stage 2'
            }
        }

        stage('Docker Image') {
            steps {
                echo "${STAGE_3}"
            }
        }
        
    }

    post {
        always {
            // Archive test results and cleanup
            junit '**/test-reports/*.xml'
            cleanWs()
        }

        failure {
            // Notify on failure (email, Slack, etc.)
            echo "Pipeline failed"
        }
    }
}