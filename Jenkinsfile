pipeline {
    agent {
        docker { image 'maven:3.9.6-eclipse-temurin-17' }  // Java + Maven ready
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run') {
            steps {
                sh 'java -cp target/hello-world-1.0-SNAPSHOT.jar HelloWorld'
            }
        }
    }

    post {
        success {
            echo "✅ Build completed successfully!"
        }
        failure {
            echo "❌ Build failed."
        }
    }
}
