node('master') {
  stage('Initialize'){
    dockerCmd '--version'
  }
}

def dockerCmd(args) {
  docker.withTool("default"){
    sh "docker ${args}"
  }
}