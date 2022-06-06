pipeline
    {
    agent any
    stages{
        stage('clone'){
            steps{
                script{
                    git credentialsId: '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', url: 'https://github.com/theerthak/flask.git'
                    
                }
            }
        }
         stage('build'){
             steps{
                 script{
                     sh '''docker build -t flask .'''
                 }
             }
         }
         stage(deploy){
             steps{
                 script{
                     sh ''' docker run -itd --name flask -p 80:5000 flask'''
                 }
             }
         }
    }    
    }
