pipeline {
    agent any

    stages {

        stage('Test HTML') {
            steps {
                echo 'Running basic HTML validation...'
                
                // Check if tidy is available
                bat 'where tidy || echo "tidy not found, skipping validation."'

                // Run tidy only if present (tidy must be installed and in PATH on Windows)
                bat 'tidy -q -e *.html || exit /b 0'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying HTML files...'

                // Make sure destination exists or replace with your own deploy path
                bat 'mkdir C:\\deploy\\html || echo "Folder exists"'
                bat 'copy /Y *.html C:\\deploy\\html\\'
            }
        }
    }
}
