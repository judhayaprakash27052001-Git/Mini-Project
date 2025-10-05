pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'master', url: 'https://github.com/judhayaprakash27052001-Git/Mini-Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t demo-webapp .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat '''
                    docker rm -f demo-web-container 2>nul
                    docker run -dit --name demo-web-container -p 8081:80 demo-webapp
                '''
            }
        }
    }
}
