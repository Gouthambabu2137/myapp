pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t myapp .'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo All tests passed!' // Replace with actual tests later
            }
        }
        stage('Deploy') {
            steps {
                echo 'Running container...'
                sh '''
                    docker rm -f myapp-container || true
                    docker run -d -p 3000:3000 --name myapp-container myapp
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed successfully!'
        }
    }
}
