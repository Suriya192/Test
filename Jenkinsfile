// Jenkinsfile
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Starting the Build Stage...'
                // Since you have a Dockerfile, a real build step might be:
                // sh 'docker build -t my-welcome-app .'
                sh 'mkdir -p build_output'
                sh 'echo "Application built successfully!" > build_output/app.txt'
                echo 'Build Stage Finished.'
            }
        }
        stage('Test') {
            steps {
                echo 'Starting the Test Stage...'
                sh 'echo "Running automated tests..."'
                sh 'echo "All tests passed!" > build_output/test_results.txt'
                echo 'Test Stage Finished.'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Starting the Deploy Stage...'
                sh 'echo "Deploying application to a dummy server..."'
                echo 'Deployment Finished.'
            }
        }
    }
    post {
        always {
            echo 'Pipeline finished. Cleaning up workspace...'
            cleanWs()
            echo 'Workspace cleaned.'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check logs for errors.'
        }
    }
}
