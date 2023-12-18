pipeline{
    agent any

    tools{
        maven 'maven3.9'
    }
    stages{
        stage("Checkout Code"){ echo "Code checkout started"
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
                deploy adapters: [tomcat9(url: 'http://50.17.154.210:8080/', credentialsId:'Tomcred01')] , war:'target/*.war'
            
            }
        }
    }
}
