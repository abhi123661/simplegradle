pipeline {
    agent any  // Use any available agent

    tools {
        gradle 'Gradle'  // Ensure this matches the name configured in Jenkins
        jdk 'JDK1'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/abhi123661/simplegradle.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'  // Run Maven build
            }
        }

       stage('Test') {
           steps {
               sh 'gradle test'  // Run unit tests
           }
        }

              
        stage('Run Application') {
            steps {
                // Start the JAR application
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
