pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'g++ new.cpp -o program'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing the project...'
                sh './program'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the project...'
                sh 'scp program user@server:/var/www/program'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
