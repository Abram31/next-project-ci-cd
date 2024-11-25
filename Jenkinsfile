pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing Dependencies'
                sh 'npm install'
                echo 'Dependencies Installed'
                sh 'npm run build'
            }
        }
    }

}
