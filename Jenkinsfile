pipeline {
    agent any

    tools {
        maven 'maven3'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Siddu-009/jenkins-java-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t siddu/java-app .'
            }
        }

        stage('Docker Push') {
            steps {
                sh 'docker login -u USER -p PASS'
                sh 'docker push siddu/java-app'
            }
        }
    }
}
