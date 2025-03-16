node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/HwangJunha/web-count.git'
    }

    stage('Build image') {
       dockerImage = docker.build("tarot10/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
