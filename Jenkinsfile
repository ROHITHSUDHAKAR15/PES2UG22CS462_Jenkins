pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/ROHITHSUDHAKAR15/PES2UG22CS462_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                sh 'g++ main/helo.cpp -o main/output'
            }
        }

        stage('Test') {
            steps {
                sh './main/output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
