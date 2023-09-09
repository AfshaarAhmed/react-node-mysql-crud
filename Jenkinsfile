pipeline {
    agent any
    stages {
        stage('Frontend Build') {
            when {
                changeset "**/server/**/*"
            }
            steps {
                // Build and deploy frontend
                sh 'cd /var/lib/jenkins/workspace/multibranch-pipeline_master && npm i'
            }
        }
        stage('Backend Build') {
            when {
                changeset "**/client/**/*"
            }
            steps {
                // Build and deploy backend
                sh 'cd multibranch-pipeline_master && npm install && npm start'
            }
        }
    }
}
