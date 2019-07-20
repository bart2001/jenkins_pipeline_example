pipeline {
    agent none
    stages {
        stage('Test') {
            agent {
                docker { image 'node:7-alpine' }
            }
            steps {
                sh 'node --version'
                sh 'touch ./newfile.txt'
                stash includes: 'newfile.txt', name: 'newfile'
                sh 'ls -al'
            }
        }
        stage('delploy to kubernetes') {
            agent any
            steps {
                unstash 'newfile'
                sh 'cat newfile.txt'
                sh 'ls -al'
                sh 'kubectl --kubeconfig ./config apply -f subpath.yaml'
            }
        }
    }
}