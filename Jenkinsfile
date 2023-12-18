pipeline{
    agent any

    tools{
        maven 'maven3.9'
    }
    stages{
        stage("Checkout Code"){
            echo "Code checkout started"
            steps{
                git branch: 'main', url: 'https://github.com/DevOpsProject-sam/java-web-app.git'
             echo "Code checkout completed"   
            }
        }
        stage("Build Code"){
            echo "Build Code started"
            steps{
                sh 'mvn clean package'
            echo "Build Code completed"
            }
        }
        stage("Deployment"){
            steps{
                deploy adapters: [tomcat9(url: 'http://50.17.154.210:8080/', credentialsId:'Tomcred01')] , war:'target/*.war'
                echo "Project deployment completed"
            }
        }
    }
}
