pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/i227433/flask-jenkins-pipeline.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Run Unit Tests') {
            steps {
                bat 'pytest tests/test_app.py'
            }
        }
        stage('Build Application') {
            steps {
                echo 'Packaging application...'
                bat 'echo Build Successful > build_log.txt'
            }
        }
        stage('Deploy Application') {
            steps {
                echo 'Deploying to target directory...'
                bat 'if not exist deploy_folder mkdir deploy_folder'
                bat 'xcopy /Y *.* .\\deploy_folder\\'
            }
        }
    }
}
