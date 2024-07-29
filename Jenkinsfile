pipeline {
    agent any
    
     tools
    {
       maven "Maven"
    }
    




stages{
        stage('Build'){
            steps {
                sh 'mvn package'
            }
     
        }

        stage ('UnitTest'){
         
                    steps {
                        sh 'mvn clean test'
                    }
                }

            
            
        }
    }
