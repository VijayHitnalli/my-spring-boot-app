pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // Jenkins pulls your code from GitHub
                checkout scm
            }
        }

        stage('Build Java App') {
            steps {
                // This runs Maven to create your target/app.jar
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Build Docker Image') {
            steps {
                // This creates the "package" using your Dockerfile
                sh 'docker build -t vijayhitnalli/my-spring-app:latest .'
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                // This sends the "package" to the internet
                sh 'docker push pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // Jenkins pulls your code from GitHub
                checkout scm
            }
        }

        stage('Build Java App') {
            steps {
                // This runs Maven to create your target/app.jar
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Build Docker Image') {
            steps {
                // This creates the "package" using your Dockerfile
                sh 'docker build -t vijayhitnalli/my-spring-app:latest .'
            }
        }
        
        stage('Push to Docker Hub') {
            steps {
                // This sends the "package" to the internet
                sh 'docker push vijayhitnalli/my-spring-app:latest'
            }
        }
    }
}/my-spring-app:latest'
            }
        }
    }
}
