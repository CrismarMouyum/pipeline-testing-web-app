pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your source code from Git
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Build your Maven project
                sh 'mvn clean install'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy your Spring Boot application here (e.g., copy to a server)
                sh 'scp target/thymeleafDemo-0.0.1-SNAPSHOT.jar ubuntu@16.171.63.242:/path/to/deployment/'
            }
        }
    }

    post {
        success {
            // Notify on successful deployment, if needed
            echo 'Deployment successful!'
        }
        failure {
            // Notify on deployment failure, if needed
            echo 'Deployment failed!'
        }
    }
}
