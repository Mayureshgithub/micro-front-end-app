pipeline {
   agent any
   stages {
    stage ('PULL'){
        steps {
           git branch: 'develop', credentialsId: 'github', url: 'https://github.com/Mayureshgithub/micro-front-end-app.git'
           sh 'ls'
        }
    }
        stage('Build') { 
        steps {
            sh '''
            sudo npm i ng-cli
            sudo npm install 
            sudo ng build
            '''
            }
        
    }
    stage('Deploy') { 
        steps {
            sh '''
            sudo aws s3 cp dist/eShopping-UI/ s3://devops-mfa-app2/ --recursive --region us-east-1    
            '''
            }
        }  
   }
}
