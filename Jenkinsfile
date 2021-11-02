pipeline {
    agent any 
    stages {
        stage('Build') {
            steps{
               sh "docker build -t nikhilkolambe/my-redis ."
                 }
        
        }
        stage('Push'){
            steps{
                withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
                sh "docker login -u nikhilkolambe -p ${dockerHubPwd}"
            }
                sh "docker push nikhilkolambe/my-redis"
            }
        }
        
        
    }
}
