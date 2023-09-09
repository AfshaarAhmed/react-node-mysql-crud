pipeline {
    agent any
    stages {
        stage('Frontend Build') {
            when {
                changeset "**/server/**/*"
            }
            steps {
                // Build and deploy frontend
                sh 'cd /var/lib/jenkins/workspace/multibranch-pipeline_master && systemctl restart nginx'
            }
        }
        stage('Backend Build') {
            when {
                changeset "**/client/**/*"
            }
            steps {
                // Build and deploy backends
                sh 'cd /var/lib/jenkins/workspace/multibranch-pipeline_master && systemctl restart nginx'
            }
        }
    }
}
