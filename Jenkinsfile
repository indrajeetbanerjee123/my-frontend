pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/indrajeetbanerjee123/my-frontend.git'
            }
        }

        stage('Deploy to S3') {
            steps {
                sh '''
                aws s3 cp index.html s3://my-frontend-bucket-7550/
                '''
            }
        }
    }
}
