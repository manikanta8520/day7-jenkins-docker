pipeline {
    agent any

    stages {

        stage('Build Image') {
            steps {
                sh 'docker build -t manikanta1228/day7-app .'
            }
        }

        stage('Login & Push') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh '''
                    echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
                    docker push manikanta1228/day7-app
                    '''
                }
            }
        }
    }
}

