pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o output PES1UG22CS192.cpp && exit 1' // Compilation fails intentionally
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './output' // Will not run if build fails
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
            }
        }
    }

    post {
        failure {
            echo '❌ Pipeline Failed ❌'
        }
    }
}
