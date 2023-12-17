pipeline{
    agent any

    tools{
        maven 'maven3.9'
    }
    stages{
        stage("Checkout Code"){
            steps{
                git branch: 'main', url: 'https://github.com/DevOpsProject-sam/java-web-app.git'
            }
        }
        stage("Build Code"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Deployment"){
            steps{
                deploy adapters: [tomcat9(url: 'http://54.172.200.236:8080/', credentialsId:'dep01tomcat')] , war:'target/*.war'
            }
        }
    }
}
