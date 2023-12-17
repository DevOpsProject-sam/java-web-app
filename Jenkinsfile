pipeline{
    agent any

    tools{
        maven 'maven3.9'
    }
    stages{
        stage("Checkout Code"){
            steps{
                git branch: 'main', url: 'https://github.com/padmanava9490/java-web-app.git'
            }
        }
        stage("Build Code"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Deployment"){
            steps{
                deploy adapters: [tomcat9(url: 'http://54.221.63.54:8080/', credentialsId:'TomcatCred')] , war:'target/*.war'
            }
        }
    }
}