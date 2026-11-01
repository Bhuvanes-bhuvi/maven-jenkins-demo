
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code checked out from GitHub'
            }
        }

        stage('Check Java and Maven') {
            steps {
                bat 'java -version'
                bat 'mvn -version'
            }
        }

        stage('Maven Clean') {
            steps {
                dir('maven') {
                    bat 'mvn clean'
                }
            }
        }

        stage('Maven Build') {
            steps {
                dir('maven') {
                    bat 'mvn install'
                }
            }
        }
    }

    post {
        success {
            echo 'Maven build completed successfully!'
        }
        failure {
            echo 'Maven build failed. Check Console Output.'
        }
    }
}
