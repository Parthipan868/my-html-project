pipeline {
    agent any

    stages {

        stage('Test HTML') {
            steps {
                echo 'Running basic HTML validation...'

                script {
                    def tidyExists = bat(
                        script: '@where tidy',
                        returnStatus: true
                    ) == 0

                    if (tidyExists) {
                        echo 'tidy found. Running validation...'
                        bat 'tidy -q -e *.html || exit /b 0'
                    } else {
                        echo 'tidy not found, skipping validation.'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying HTML files...'

                bat '''
                    if not exist C:\\deploy\\html (
                        mkdir C:\\deploy\\html
                    )
                    copy /Y *.html C:\\deploy\\html\\
                '''
            }
        }
    }
}
