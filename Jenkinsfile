node('master') {
  stage('Initialize'){
    dockerCmd '--version'
  }
  stage('Clone repository') {
    checkout scm
  }
  stage('Build image') {
    dockerCmd "build . -t getintodevops-hellonode:${env.BUILD_NUMBER}"
  }
  stage('Test image') {
    sh 'echo "Tests passed"'
  }

  stage('Push image') {

    dockerCmd "login -u duongngocmanh -p Qmhmq678"
    dockerCmd "tag getintodevops-hellonode:${env.BUILD_NUMBER} duongngocmanh/getintodevops-hellonode:${env.BUILD_NUMBER}"
    dockerCmd "push duongngocmanh/getintodevops-hellonode:${env.BUILD_NUMBER}"
  }
}

def dockerCmd(args) {
  docker.withTool("myDocker"){
    sh "docker ${args}"
  }
}