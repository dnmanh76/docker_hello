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
  
}

def dockerCmd(args) {
  docker.withTool("myDocker"){
    sh "docker ${args}"
  }
}