pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'repository_url'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Execute Test') {
            steps {
                bat 'python test.py'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main') {
                        echo 'Deploying to production'
                    } else {
                        echo 'Deploying to UAT'
                    }
                }
            }
        }
    }
}
