pipeline{
    
    agent any
    
    stages{
        stage('SCM'){
            steps{
                git 'https://github.com/keshavmlsaini/jenkins-docker-maven-java-webapp.git'
            }
        }
        stage('Build by Maven'){
            steps{
                sh 'mvn clean package'
            }
        }
    }
}
