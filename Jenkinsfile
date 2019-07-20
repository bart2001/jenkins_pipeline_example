pipeline {
    agent any
    stages {
        stage('Test') {
            agent docker { image 'node:7-alpine' }
            steps {
                sh 'node --version'
                sh 'touch ./newfile.txt'
                stash includes: '*', name: 'builtSources'
                sh 'ls -al'
            }
        }
        stage('delploy to kubernetes') {
            agent any
            steps {
                unstash 'builtSources'
                sh 'ls -al'
                //sh 'kubectl --kubeconfig ./config apply -f subpath.yaml'
            }
        }
    }
}