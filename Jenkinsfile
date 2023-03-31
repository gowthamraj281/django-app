pipeline {
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/gowthamraj281/django-app.git']]])
                bat 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    bat 'docker build -t gowthamraj281/devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   bat 'docker login -u gowthamraj281 -p dckr_pat_q9iBrTujk8VqNm0axC4pZUwPBgk'
                   bat 'docker push gowthamraj281/devops-integration'
                }
            }
        }
        stage('Deploy to k8s'){
            steps{
                script{
                    kubernetesDeploy (configs: 'deploymentservice.yaml',kubeconfigId: 'kubeconfig')
                }
            }
        }
        stage('remove docker image'){
            steps{
                script{
                    bat 'docker rmi gowthamraj281/devops-integration'
                }
            }
        }
    }
}
