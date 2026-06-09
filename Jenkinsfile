pipeline {
agent any

stages {

    stage('Verify Files') {
        steps {
            sh 'ls -la'
        }
    }

    stage('Deploy to S3') {
        steps {
            sh '''
            aws s3 sync . s3://my-frontend-bucket-7550 --delete \
            --exclude ".git/*" \
            --exclude "Jenkinsfile"
            '''
        }
    }
}

post {
    success {
        echo 'Website deployed successfully to S3'
    }

    failure {
        echo 'Pipeline failed'
    }
}

}
