pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Parthipan868/my-html-project.git'
            }
        }

        stage('Test HTML') {
            steps {
                sh 'echo "Running basic HTML validation..."'
                // If tidy is installed, this will report issues; `|| true` prevents failure
                sh 'tidy -q -e *.html || true'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying HTML files..."'
                // Copy HTML files to web server directory (edit path if needed)
                sh 'cp *.html /var/www/html/'
            }
        }
    }
}
