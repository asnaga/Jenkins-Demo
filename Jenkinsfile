pipeline {
    agent any
 
    environment {
        NODE_ENV = 'development'
    }
 
    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning Repository...'
git url: 'https://github.com/asnaga/Jenkins-Demo.git', branch: 'main'
            }
        }
 
        stage('Install Dependencies') {
            steps {
                echo 'Installing Node Modules...'
                sh 'npm install'
            }
        }
 
        stage('Run Tests') {
            steps {
                echo 'Running Tests...'
                sh 'npm test'
            }
        }
 
        stage('Build') {
            steps {
                echo 'Building the Project...'
                sh 'npm run build'
            }
        }
 
        stage('Archive Artifacts') {
            steps {
                echo 'Archiving the build output...'
                archiveArtifacts artifacts: 'build/**', fingerprint: true
            }
        }
 
        stage('Deploy to Test Environment') {
            steps {
                echo 'Deploying to test server (mock)...'
                // Dummy deploy command, can be replaced with actual scp/kubectl/ssh commands
                sh 'echo "Deploying build to test environment..."'
            }
        }
    }
 
    post {
        success {
            echo 'Pipeline executed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
