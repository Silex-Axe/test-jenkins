pipeline {
    agent any
    environment {
        STAGE_3 = 'Stagee 3'
    }
    stages {
        stage('Stage 1') {
            steps {
                echo 'Stagee 1'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'Stagee 2'
            }
        }

        stage('Stage 3') {
            steps {
                echo "${STAGE_3}"
            }
        }

        stage('Test') {
            steps {
                stage4().call()
            }
        }
    }

    post {
        always {
            // Archive test results and cleanup
            cleanWs()
        }

        failure {
            // Notify on failure (email, Slack, etc.)
            echo 'Pipeline failed'
        }
    }
}

def stage4() {
    return {
        stage('Stage 4') {
            steps {
                echo 'Stagee 4'
            }
        }
    }
}
