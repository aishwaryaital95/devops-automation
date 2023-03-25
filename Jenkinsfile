pipeline {
    agent any
    tools{
        maven 'maven'
    }
    
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/sureshrajuvetukuri/devops-automation.git']]])
                sh 'mvn clean install'
            }
        }
       
        
        
         stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t aish1320/kubernetes .'
                }
            }
        
        
             
             
             
             
    }
        
        stage('Push image to hub'){
            steps{
                script{
                    withCredentials([string(credentialsId: 'dockerhubpwd1', variable: 'dockerhubpwd1')]) {
 
                    
                    sh 'docker login -u aish1320 -p ${dockerhubpwd1}'
                        
                    }
                    sh 'docker push aish1320/kubernetes'
                }
            }
        }
        
    }
}
