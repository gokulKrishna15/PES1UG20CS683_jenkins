pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o gok683 gok683.cpp'
            }
        }

        stage('Test') {
            steps {
                sh './gok683'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deployed successfully'
            }
        }
    }

    post {
        always {
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'pipeline failed'
                }
            }
        }
    }
}
