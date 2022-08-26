pipeline{
    
    agent any
    
    stages{
            stage('Initialize')
    {
        def dockerHome = tool 'MyDocker'
        def mavenHome  = tool 'MyMaven'
        env.PATH = "${dockerHome}/bin:${mavenHome}/bin:${env.PATH}"
    }
        stage('SCM'){
            steps{
                git 'https://github.com/Roopamrc3/jenkins-docker-maven-java-webapp'
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
