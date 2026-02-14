pipeline {
    agent any

    stages {

        stage('Build Image') {
            steps {
                sh 'docker build -t manikanta1228/day7-app .'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push manikanta1228/day7-app'
            }
        }
    }
}
