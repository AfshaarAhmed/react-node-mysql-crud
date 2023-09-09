pipeline {
    agent any
    stages {
        stage('Frontend Build') {
            when {
                changeset "**/edu-react/**/*"
            }
            steps {
                // Build and deploy frontend
                sh 'cd edu-react && npm install && npm run build'
            }
        }
        stage('Backend Build') {
            when {
                changeset "**/edu-node/**/*"
            }
            steps {
                // Build and deploy backend
                sh 'cd edu-node && npm install && npm start'
            }
        }
    }
}
