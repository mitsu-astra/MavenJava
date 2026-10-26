pipeline {
    agent any

    tools {
        maven 'Maven-3.9.16'
    }

    stages {
        stage('git repo & clean') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('install') {
            steps {
                sh 'mvn install'
            }
        }

        stage('test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Check the console output.'
        }
    }
}
