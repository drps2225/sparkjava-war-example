pipeline {
    agent {
        label 'maven-agent' // Use an agent with Maven installed
    }

    environment {
        PATH = "/opt/maven/bin:$PATH" // Add Maven to PATH if not already available
        GITHUB_REPO = 'https://github.com/your-username/your-repo.git'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git url: "${GITHUB_REPO}", branch: 'main'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }
        failure {
            echo 'Something went wrong with the build or tests.'
        }
    }
}

