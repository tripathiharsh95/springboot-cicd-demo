pipeline {
    agent any

    tools {
        maven 'Maven3'
    }

    environment {
        PROJECT_NAME = "Maven Demo"
    }

    stages {

        stage('Build') {
            steps {
                echo "Building ${PROJECT_NAME}"
                bat 'mvn clean package'
            }
        }

        stage('Archive') {
             steps {
                 archiveArtifacts artifacts: 'target/*.jar'
             }
        }

    }

    post {

        success {
            echo "Build Successful"
        }

        failure {
            echo "Build Failed"
        }

        always {
            echo "Pipeline Finished"
        }

    }

}