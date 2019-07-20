pipeline {
    agent none
    stages {
        stage('Test') {
            agent docker { image 'node:7-alpine' }
            steps {
                sh 'node --version'
                sh 'touch ./newfile.txt'
            }
        }
        stage('delploy to kubernetes') {
            agent any
            steps {
                sh 'ls -al'
                sh 'kubectl --kubeconfig ./config apply -f subpath.yaml'
            }
        }
    }
}