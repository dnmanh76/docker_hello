node('master') {
  stage('Initialize'){
    dockerCmd '--version'
  }
}

def dockerCmd(args) {
  docker.withTool("myDocker"){
    sh "docker ${args}"
  }
}