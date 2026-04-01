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
                // This block securely fetches the password you saved in Jenkins
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', passwordVariable: 'DOCKER_HUB_PASSWORD', usernameVariable: 'DOCKER_HUB_USERNAME')]) {
                    // Use double quotes (") here so Jenkins can swap the variables
                    sh "docker login -u ${DOCKER_HUB_USERNAME} -p ${DOCKER_HUB_PASSWORD}"
                    sh "docker push vijay2021/my-spring-app:latest"
                }
            }
        }
    }
}
