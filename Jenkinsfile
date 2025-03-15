pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the project...'
                    sh 'g++ -o YOUR_SRN-1 program.cpp' // Replace 'program.cpp' with your actual file name
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                    sh './YOUR_SRN-1' // Running the compiled C++ executable
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
