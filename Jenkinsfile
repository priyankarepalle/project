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
        stage('Sonar Analysis') {
            steps {
                echo 'Sonar Analysis.....'
                sh 'mvn test sonar:sonar
                    -Dsonar.host.url=http://107.20.121.249:9000 
                    -Dsonar.login=d1854b1fb3df7df4777a2ece6bba5ad242a2c324'
            }          
        } 
       stage('Publish-release') {
            steps {
                echo 'Release....'
                sh 'mvn deploy'
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
