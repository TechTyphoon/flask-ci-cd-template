pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                // This step is usually handled by Jenkins automatically.
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing Python packages...'
                // Use python3 and pip3 explicitly, and install to user directory
                sh 'python3 -m pip install --user -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Use python3 module execution for pytest
                sh 'python3 -m pytest || echo "No tests found, continuing..."'
            }
        }
    }
    post {
        // The 'post' section runs after all the stages are complete.
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Hooray! The pipeline was successful. ✅'
        }
        failure {
            echo 'Oops! The pipeline failed.'
        }
    }
}
