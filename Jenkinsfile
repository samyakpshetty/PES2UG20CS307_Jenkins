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
            when {
              expression {
                currentBuild.result == null || currentBuild.result == 'SUCCESS' 
              }
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
