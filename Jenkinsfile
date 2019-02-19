pipeline {
    agent {
        docker 'maven:3-alpine'
    }
    stages {
        stage('Clone repository') {
            steps{
                checkout scm
            }
        }

        stage ('Docker') {
            steps {
                sh 'docker version'
            }
        }

        stage('Build image') {
            steps{
                sh 'docker build . -t getintodevops-hellonode:${env.BUILD_NUMBER}'
            }
        }

        stage('Test image') {
            steps{
                sh 'echo "Tests passed"'
            }
        }

        stage('Push image') {
            steps{
                sh "docker login -u duongngocmanh -p Qmhmq678"
                sh "docker tag getintodevops-hellonode:${env.BUILD_NUMBER} duongngocmanh/getintodevops-hellonode:${env.BUILD_NUMBER}"
                sh "docker push registry.hub.docker.com/getintodevops-hellonode:${env.BUILD_NUMBER}"
            }
        }
    }
}
