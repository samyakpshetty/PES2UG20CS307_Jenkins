pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'g++ new.cpp -o PES2UG20CS307-1'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing the project...'
                sh './PES2UG20CS307-1'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the project...'
                sh 'scp PES2UG20CS307-1 PES2UG20CS307@server:/var/www/program'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
