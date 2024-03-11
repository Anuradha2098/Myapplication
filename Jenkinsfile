pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Checkout source code from GitHub
             //   git url: 'https://github.com/your-username/your-repository.git'
              git url: 'https://github.com/Anuradha2098/Myapplication.git'
                // Build the project using Maven
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                // Run tests using Maven
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                // Deploy the built artifact (assuming it's a JAR file) to a server
                // Replace user, server, and path with your actual deployment details
                sh 'scp target/my-app.jar user@server:/path/to/deploy'
            }
        }
    }
}
