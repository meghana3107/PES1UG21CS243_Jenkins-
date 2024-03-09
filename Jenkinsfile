pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Compile the C++ code
                sh g++ task5.cpp -o output
            }
        }

        stage('Test') {
            steps {
                // Execute the compiled program and capture the output
                script {
                    def output = sh(script: './output', returnStdout: true).trim()
                    println "Program Output: ${output}"
                }
            }
        }

        stage('Deploy') {
            steps {
                // Add deployment steps here if needed
                echo 'Deploying...'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
