pipeline {
    agent {
        docker {
            image 'python:3.10-slim'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out code from GitHub...'
                git branch: 'main', url: 'https://github.com/code-and-brain/odoo_18_template.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image for Odoo...'
                script {
                    sh 'docker build -t odoo_18_template_image .'
                }
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests (This is a placeholder stage).'
                // In a real project, you would add commands to run tests here.
                // For example: sh 'docker run --rm odoo_18_template_image pytest'
                sh 'echo "Tests passed!"'
            }
        }
    }
}