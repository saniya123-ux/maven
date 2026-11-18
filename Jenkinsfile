
pipeline {
    agent any
    tools {
        maven 'Maven3' 
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application locally...'
                bat 'if not exist deploy mkdir deploy'
                bat 'copy target\\*.jar deploy\\'
            }
        }
    }
}
