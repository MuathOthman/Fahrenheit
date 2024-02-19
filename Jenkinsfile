pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Runs Maven's clean and package phases, which compiles your project and packages it into a JAR/WAR (without running unit tests)
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Runs Maven's test phase to execute your unit tests
                sh 'mvn test'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
