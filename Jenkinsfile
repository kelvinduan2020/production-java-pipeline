pipeline{
    agent{
        label "jenkins-agent"
    }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage("Cleanup Workspace"){
            steps {
                cleanWs()
            }

        }    
        stage("Checkout Code"){
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/kelvinduan2020/production-java-pipeline.git'
            }

        }   
        stage("Build Application"){
            steps {
                sh 'maven clean package'
            }

        }   
        stage("Test Application"){
            steps {
                sh 'maven test'
            }

        }
    }
}