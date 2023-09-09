pipeline {
    agent any
    stages {
        stage('Frontend Build') {
            when {
                changeset "**/server/**/*"
            }
            steps {
                // Build and deploy frontend
                sh 'cd react-node-mysql-crud && npm i'
            }
        }
        stage('Backend Build') {
            when {
                changeset "**/client/**/*"
            }
            steps {
                // Build and deploy backend
                sh 'cd react-node-mysql-crud && npm install && npm start'
            }
        }
    }
}
