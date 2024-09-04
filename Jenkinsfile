pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                git changelog: false, poll: false, url: 'https://github.com/maheshbasapur/experiment.git'
            }
        }
/*
        stage('Docker Build and Push') {
            steps {
                script {
                    withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'my-docker-hub-credential', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD']]) {
                        sh "docker build -t vaibhav220622/react_jenkins:v1 ."
                        sh "docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD"
                        sh "docker push vaibhav220622/react_jenkins:v1"
                    }
                }
            }
        } 
*/
        
        stage('Deploy to Minikube') {
            steps {
                sh 'kubectl apply -f my-react-deployments.yaml'
            }
        }
    }
}
