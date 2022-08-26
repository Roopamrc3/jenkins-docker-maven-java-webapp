pipeline{
    
    agent any
    
    stages{
        stage('SCM'){
            steps{
                git 'https://github.com/keshavmlsaini/jenkins-docker-maven-java-webapp.git'
            }
        }
        stage('Run Task'){
            steps{
                sh '''
                docker build -t sample:${BUILD_NUMBER} .
                docker run --name sample -d -p 80:8081 sample:${BUILD_NUMBER}
                '''
            }
        }
    }
}
