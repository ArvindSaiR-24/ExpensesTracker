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


        stage('Build and Run') {
            steps {
                script {
                    // Run the Spring Boot application
                    echo 'Running the Spring Boot application'
                    cmd "/c mvn spring-boot:run"
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
