pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out the project from version control
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Build the Maven project
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            // Archive the WAR file as a build artifact
            archiveArtifacts 'target/*.war'
        }
    }
}
