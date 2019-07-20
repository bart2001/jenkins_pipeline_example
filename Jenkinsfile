pipeline {
    agent {
        docker { image 'node:7-alpine' }
    }
    stages {
        stage('delploy to kubernetes') {
            steps {
                sh 'kubectl --kubeconfig ./config apply -f subpath.yaml'
            }
        }
    }
}