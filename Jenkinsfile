node {
    def app
    def dockerTool = tool name: 'myDocker', type: 'org.jenkinsci.plugins.docker.commons.tools.DockerTool'
    withEnv(["DOCKER=${dockerTool}/bin"]) {
      //stages
      //now we can simply call: dockerCmd 'run mycontainer'
    }

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("duongngocmanh/getintodevops/hellonode")
    }

    stage('Test image') {
        app.inside {
            sh 'echo "Tests passed"'
        }
    }

    stage('Push image') {
        dockerCmd 'push duongngocmanh/getintodevops/hellonode:${env.BUILD_NUMBER}'
    }
}
def dockerCmd(args) {
    sh "${DOCKER}/docker ${args}"
}
