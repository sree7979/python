pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.build("my-devops-project")
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    docker.image('my-devops-project').inside {
                        sh 'pip install -r requirements.txt'
                        sh 'python -m unittest discover tests'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Add deployment steps here
                    echo 'Deployment steps go here'
                }
            }
        }
    }
}

