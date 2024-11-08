pipeline {
    agent any

    node {
        //environment().call()
        stage4().call()
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

        stage('Stage 3') {
            steps {
                echo "${STAGE_3}"
            }
        }
        script{
        stage4()
        }
    }

    post {
        always {
            // Archive test results and cleanup
            cleanWs()
        }

        failure {
            // Notify on failure (email, Slack, etc.)
            echo "Pipeline failed"
        }
    }
}

def environment (){
    return 
    {
        environment {
        STAGE_3="Stage 3"
    }
    }
}
def stage4() {
    return {
         stage('Stage 4') {
    
                steps {
                echo "Stage 4"
            }
        }
    }
}