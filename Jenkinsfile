pipeline {
    agent {
        docker {
            image 'docker:latest'
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
                sh 'docker build -t odoo_18_template_image .'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests (This is a placeholder stage).'
                sh 'echo "Tests passed!"'
            }
        }
    }
}