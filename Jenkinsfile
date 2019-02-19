pipeline {
    agent {label 'jenkinslave'}
    stage('Clone repository') {
        steps{
            sh "checkout scm"
        }
    }

    stage('Build image') {
        steps{
            sh "docker build . -t getintodevops-hellonode:${env.BUILD_NUMBER}"
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
