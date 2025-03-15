pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the project...'
                    sh 'g++ -o hello.cpp' // Replace 'program.cpp' with your actual file name
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh './PES2UG22CS154-1' // Running the compiled C++ executable
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying application...'
                    sh 'echo "Deployment successful!"' // Simulated deploy step
                }
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
