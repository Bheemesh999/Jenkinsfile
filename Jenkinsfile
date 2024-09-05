pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'http://github.com/Bheemesh999/GroceryStore.git'
'
            }
        }
        stage('Build') {
            steps {
                sh './mvnw clean install'
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test'
            }
        }
        stage('Package') {
            steps {
                sh './mvnw package'
            }
        }
        stage('Deploy to Staging') {
            steps {
                sh './deploy.sh staging'
            }
        }
    }

    post {
        success {
            mail to: 'Bheemeshguthi1@gmail.com',
                 subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                 body: "Good news! The job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' succeeded."
        }
        failure {
            mail to: 'team@example.com',
                 subject: "FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                 body: "Unfortunately, the job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed."
        }
    }
}
error: src refspec main does not match any
error: failed to push some refs to 'origin'
