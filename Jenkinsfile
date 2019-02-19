node('master') {
  def dockerTool = tool name: 'myDocker', type: 'org.jenkinsci.plugins.docker.commons.tools.DockerTool'
  withEnv(["DOCKER=${dockerTool}/bin"]) {

  }
  stage('Initialize'){
    dockerCmd '--version'
  }
}

def dockerCmd(args) {
    sh "sudo ${DOCKER}/docker ${args}"
}