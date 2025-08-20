pipeline {
    agent any

    stages {
        stage('Validate the code') {
            steps {
                sh 'mvn validate'
            }
        }

        stage('Compile & Build the App') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test the App') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished!'
        }
        success {
            echo 'Build succeeded'
        }
        failure {
            echo 'Build failed'
        }
    }
}
