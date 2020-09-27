pipeline {
    agent any

    stages {
        stage('Code Validation') {
            steps {
                echo 'Validating & Compiling'
                sh 'mvn validate compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing.....' 
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'mvn package' 
            }
        }
    }
}
