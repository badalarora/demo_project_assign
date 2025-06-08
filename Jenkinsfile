
pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/badalarora/demo_project_assign.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker run -d -p 99:80 --name website mywebsite'
            }
        }
    }
    triggers {
        githubPush()
    }
}
