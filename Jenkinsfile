node {
    withDockerContainer(image: 'node:16-buster-slim',args: '-p 3000:3000'){
    checkout scm
    stage('Build') {
    sh 'npm install'   
    }
    stage('Test') {
    withDockerContainer(image: 'qnib/pytest', args:'-i --entrypoint=""'){
    sh './jenkins/scripts/test.sh'
        }
    }
  }
}
