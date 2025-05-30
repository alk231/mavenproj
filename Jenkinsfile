pipeline {
    agent any
    tools {
        maven 'Maven 3.9.9'
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/alk231/mavenproj.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }
    post {
        success {
            echo '🎉 Build and Test Passed!'
        }
        failure {
            echo '🚨 Build Failed!'
        }
    }
}
