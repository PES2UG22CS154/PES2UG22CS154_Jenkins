pipeline {
    agent any

    stages {
        stage('Setup') {
            steps {
                sh 'g++ --version || { echo "g++ not found"; exit 1; }'
            }
        }

        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/PES2UG22CS154/PES2UG22CS154_Jenkins.git', credentialsId: 'github-pat']]
                ])
            }
        }

        stage('Build') {
            steps {
                sh 'g++ main/hello.cpp -o main/output > build.log 2>&1 || { echo "Build failed"; exit 1; }'
            }
        }

        stage('Test') {
            steps {
                sh 'test -f main/output && ./main/output > test_output.log 2>&1 || { echo "Executable not found or test failed"; exit 1; }'
                sh 'cat test_output.log'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy placeholder (replace with actual deployment logic)'
                // Example: sh 'scp main/output user@remote-server:/path/to/deploy/'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed. Check the logs for details.'
            sh 'cat build.log || true'
            sh 'cat test_output.log || true'
            error 'Pipeline failed'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}
