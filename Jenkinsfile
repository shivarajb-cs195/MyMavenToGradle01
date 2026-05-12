pipeline {
    agent any

    tools {
        jdk 'JDK'
        gradle 'Gradle'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'java -version'
                sh 'gradle clean build'
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'
            }
        }

        stage('Run Application') {
            steps {
                sh 'gradle run'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
