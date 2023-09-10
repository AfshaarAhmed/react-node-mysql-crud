pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Check out the source code from the Git repository
                checkout scm
            }
        }
        stage('Frontend Build') {
            when {
                changeset "**/server/**/*"
            }
            steps {
                // Build and deploy frontend
                sh 'cd edu-react && npm install && npm run build'
            }
        }
        stage('Backend Build') {
            when {
                changeset "**/client/**/*"
            }
            steps {
                // Build and deploy backend
                sh 'cd /var/lib/jenkins/workspace/multibranch-pipeline_master && sudo systemctl restart nginx'
            }
        }
    }
}
