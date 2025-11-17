pipeline {
    agent {
        docker {
            image 'maven:3.9.6-eclipse-temurin-17'
            args '-v /root/.m2:/root/.m2'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo '🛠️ Building the project...'
                sh 'mvn clean package'
            }
        }

        stage('Run') {
            steps {
                echo '🚀 Running HelloWorld...'
                sh 'java -cp target/hello-world-1.0-SNAPSHOT.jar HelloWorld'
            }
        }
    }

    post {
        success {
            echo '✅ Build and Run successful!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}