pipeline {
    agent any
    
    stages {
        stage('Clone repository') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/Thaman-N/PES1UG22CS656_Jenkins.git']]
                ])
            }
        }
        
        stage('Build') {
            steps {
                sh 'g++ maian.cpp -o output'
                echo 'Build Stage Successful'
            }
        }
        
        stage('Test') {
            steps {
                sh './output'
                echo 'Test Stage Successful'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
