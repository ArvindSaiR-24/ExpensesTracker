pipeline {
    agent any

    environment {
        MAVEN_HOME = 'C:/ProgramData/chocolatey/lib/maven/apache-maven-3.9.9'  
        JAVA_HOME = 'C:/Program Files/Java/jdk-21/'  
    }

    stages {
        stage('Checkout') {
            steps {
                // Pull the code from the repository
                checkout scm
            }
        }

        stage('Build and Package') {
            steps {
                script {
                    // Build and package the Spring Boot application
                    echo 'Building and packaging the application'
                    sh "'${MAVEN_HOME}/bin/mvn' clean package"
                }
            }
        }

        stage('Run') {
            steps {
                script {
                    // Run the Spring Boot application
                    echo 'Running the Spring Boot application'
                    sh "java -jar target/*.jar"
                }
            }
        }
    }

    post {
        success {
            echo 'Build and run successful!'
        }
        failure {
            echo 'Build or run failed!'
        }
    }
}
