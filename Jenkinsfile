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
        stage('Deploy to Tomcat') {
            environment {
                TOMCAT_URL = 'http://admin:admin@localhost:7000/manager/text'
                WAR_FILE = 'target/my-app.war'
            }
            steps {
                // Deploy the WAR file to Tomcat using curl
                sh "curl -v -T $WAR_FILE $TOMCAT_URL --user admin:admin"
            }
        }
    }
}
