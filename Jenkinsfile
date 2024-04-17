pipeline {
    agent any
    
    stages {
        
        stage("code"){
            steps{
                git url: "https://github.com/hrdyq/DevOps-Pipeline-Project.git", branch: "master"
                echo 'code cloned'
            }
        }
        stage("build and test"){
            steps{
                sh "docker build -t devopsproject ."
                echo 'code build successful'
            }
        }
        stage("scan image"){
            steps{
                echo 'image scanning complete'
            }
        } 
         stage("deploy"){
            steps{
                sh "docker rm -f docker"
                sh "docker run -d -p 8000:8000 --name docker devopsproject:latest"
                echo 'deployment completed'
            	}
	}
	stage("")
       }   
}
