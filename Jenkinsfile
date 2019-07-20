pipeline {
    agent any
    //agent {
        //docker { image 'node:7-alpine' }
    //    any
    //}
    stages {
        stage('delploy to kubernetes') {
            steps {
                sh 'kubectl --kubeconfig ./config apply -f subpath.yaml'
            }
        }
    }
}