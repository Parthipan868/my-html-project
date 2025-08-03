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
                bat 'echo Running basic HTML validation...'
                // Skipping actual tidy command unless installed
                bat 'echo Tidy not available on Windows. Skipping validation.'
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo Deploying HTML files...'
                // This copies all .html files to IIS web directory (adjust if needed)
                bat 'xcopy /Y *.html C:\\inetpub\\wwwroot\\'
            }
        }
    }
}
