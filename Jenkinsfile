node { 
    stage('Clone repository') { 
        git credentialsId: 'github-access', url: 'https://github.com/Ducaster/docker-project-front.git' 
    } 
 
    stage('Build image') { 
       dockerImage = docker.build("ducaster/node-front:1.0") 
    } 
 
 stage('Push image') { 
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) { 
        dockerImage.push() 
        } 
    } 
} 
