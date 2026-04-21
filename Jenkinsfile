pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t bhawna930/jenkin_test .'
            }
        }

        stage('Run Container') {
            steps {
                bat '''
                docker stop my-app || exit 0
                docker rm my-app || exit 0
                docker run -d -p 3000:3000 --name my-app bhawna930/jenkin_test
                '''
            }
        }
    }
}