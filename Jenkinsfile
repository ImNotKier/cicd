<<<<<<< HEAD
<<<<<<< HEAD
=======
>>>>>>> 01654a4 (Recreate CI/CD lab files)
pipeline {
    agent any

    environment {
<<<<<<< HEAD
        JAVA_HOME = "/opt/java17"
        DEPLOY = "/var/www/html"
=======
        GIT_REPO_URL = 'https://github.com/ImNotKier/cicd.git'
        GIT_CREDENTIALS_ID = 'github-pat'
        GIT_BRANCH = 'main'
>>>>>>> 01654a4 (Recreate CI/CD lab files)
    }

    stages {

<<<<<<< HEAD
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ImNotKier/cicd.git',
                    credentialsId: 'github-pat'
            }
        }

        stage('Setup Python') {
=======
        stage('Checkout SCM') {
            steps {
                checkout scm: [
                    $class: 'GitSCM',
                    branches: [[name: "*/${env.GIT_BRANCH}"]],
                    userRemoteConfigs: [[
                        url: "${env.GIT_REPO_URL}",
                        credentialsId: "${env.GIT_CREDENTIALS_ID}"
                    ]]
                ]
            }
        }

        stage('Setup Python Environment') {
>>>>>>> 01654a4 (Recreate CI/CD lab files)
            steps {
                sh '''
                python3 -m venv venv
                . venv/bin/activate
<<<<<<< HEAD
=======
                pip install --upgrade pip
>>>>>>> 01654a4 (Recreate CI/CD lab files)
                pip install -r requirements.txt
                '''
            }
        }

<<<<<<< HEAD
        stage('Start Apache') {
            steps {
                sh 'sudo systemctl start apache2'
            }
        }

        stage('Test') {
            steps {
                sh '''
                . venv/bin/activate
                Xvfb :99 -screen 0 1024x768x16 &
                export DISPLAY=:99
                sleep 3
=======
        stage('Run Selenium Test') {
            steps {
                sh '''
                . venv/bin/activate
>>>>>>> 01654a4 (Recreate CI/CD lab files)
                python test.py
                '''
            }
        }

<<<<<<< HEAD
        stage('Deploy') {
            steps {
                sh '''
                rsync -av --delete ./ ${DEPLOY}/
                sudo chown -R www-data:www-data ${DEPLOY}
                sudo chmod -R 755 ${DEPLOY}
=======
        stage('Deploy to Apache') {
            steps {
                sh '''
                sudo rsync -av --delete ./ /var/www/html/
                sudo chown -R www-data:www-data /var/www/html/
>>>>>>> 01654a4 (Recreate CI/CD lab files)
                '''
            }
        }
    }
<<<<<<< HEAD
=======
environment {
    GIT_REPO_URL = 'https://github.com/ImNotKier/cicd.git'
    GIT_CREDENTIALS_ID = 'github-pat'
    GIT_BRANCH = 'main'
>>>>>>> 0c520e6 (Updated)
=======
>>>>>>> 01654a4 (Recreate CI/CD lab files)
}
