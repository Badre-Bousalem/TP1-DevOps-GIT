pipeline {
    agent any
   stages {
        stage('Checkout') {
            steps {
               git url:'https://github.com/aminebaha/TP1-DevOps-GIT.git', branch: 'main'

            }

        }
        stage('Build the application') {
            steps {
            sh "mvn clean install"
            }

        }
         stage('Test App') {
            steps {
            sh "mvn test"
            }
        }
        stage('Build Docker Img') {
            steps {
            sh "docker build . -t my-app"
            }
        }
        stage('Push docker image to registry') {
            steps {
                bat 'docker login -u amineazeeza -p mdpp'
                bat 'docker push amineazeeza/my-app:1.0'
            }
        }

    }

}