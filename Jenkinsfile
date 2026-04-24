pipeline {
    agent any

    environment {
        APP_NAME = "dora-test2"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Repo checkout edildi: ${env.GIT_BRANCH}"
                echo "Commit: ${env.GIT_COMMIT}"
            }
        }

        stage('Build') {
            steps {
                echo "Build aşaması başladı..."
                sh 'echo "Building ${APP_NAME} - Build #${BUILD_NUMBER}"'
            }
        }

        stage('Test') {
            steps {
                echo "Test aşaması çalışıyor..."
                sh 'echo "All tests passed!"'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy aşaması..."
                sh 'echo "Deployed successfully at $(date)"'
            }
        }
    }

    post {
        success {
            echo "Pipeline başarıyla tamamlandı! Build #${BUILD_NUMBER}"
        }
        failure {
            echo "Pipeline başarısız oldu! Build #${BUILD_NUMBER}"
        }
    }
}
