pipeline {
    agent any
    stages {
         stage('Clone repository') {
             steps {
                 checkout([$class: 'GitSCM',
                 branches: [[name: '*/main']],
                 userRemoteConfigs: [[url: 'https://github.com/dauntless05/Anshita_PES2UG22CS081.git']]])
             }
         }

        stage('Build') {
            steps {
                build 'PES2UG22CS081-1'
                sh 'g++ hello.cpp -o output'  
            }
        }

        stage('Test') {
            steps {
                sh './output'
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
