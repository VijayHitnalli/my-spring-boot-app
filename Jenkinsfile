pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // This pulls your code from GitHub
                checkout scm
            }
        }

        stage('Build Java App') {
            steps {
                // Use bat for Windows, sh for Linux
                // If you are on Windows, change 'sh' to 'bat'
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Replace 'vijay2021' with your actual Docker Hub ID
                sh 'docker build -t vijay2021/my-spring-app:latest .'
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                // Replace 'vijay2021' with your actual Docker Hub ID
                sh 'docker push vijay2021/my-spring-app:latest'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                // This 'withCredentials' block handles the login automatically
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', passwordVariable: 'Vijay@1743', usernameVariable: 'vijay2021')]) {
                    sh "docker login -u ${vijay2021} -p ${Vijay@1743}"
                    sh "docker push vijay2021/my-spring-app:latest"
                }
            }
        }
    }
}
