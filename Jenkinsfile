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
        
        
    }
}
