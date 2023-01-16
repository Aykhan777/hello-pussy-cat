pipeline {
    agent any

    stages {
        stage('build') {
            steps{
                echo "bulid doker"
                sh "docker build -t meowsobaka/wsadrf:v$BUILD_ID ."
            }
        }
        stage('push doker hub'){
            steps {
                    withCredentials([usernamePassword(credentialsId: 'docker-hub', passwordVariable: 'password', usernameVariable: 'username')]) {
                    sh "docker login -u $username -p $password"
                    sh "docker push meowsobaka/wsadrf:v$BUILD_ID"
                }
             }
        }
    }
}
