pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t rajhub22/website:latest .'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying Docker container...'
                bat 'docker stop website || exit 0'
                bat 'docker rm website || exit 0'
                bat 'docker run -d -p 80:80 --name website rajhub22/website:latest'
            }
        }
    }
}
