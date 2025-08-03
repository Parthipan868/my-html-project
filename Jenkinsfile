pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/Parthipan868/my-html-project.git'
            }
        }

        stage('Test HTML') {
            steps {
                sh 'echo "Running basic HTML validation..."'
                sh 'tidy -q -e *.html || true'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying HTML files..."'
                sh 'cp *.html /var/www/html/'
            }
        }
    }
}
