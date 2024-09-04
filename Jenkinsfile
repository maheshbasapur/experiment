pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                git changelog: false, poll: false, url: 'https://github.com/maheshbasapur/experiment.git'
            }
        }
        
        stage('Deploy to Minikube') {
            steps {
                sh 'kubectl apply -f my-react-deployments.yaml'
            }
        }
    }
}
