pipeline {
    agent docker { image 'nginx:latest' }
    stages {
        stage('Check') {
            steps {
                sh 'pwd'
                sh 'ls -al'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
