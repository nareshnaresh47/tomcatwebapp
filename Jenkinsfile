pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/nareshnaresh47/tomcatwebapp.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    def server = 'http://13.201.71.133:8080'
                    def warFile = 'target/DevOpsWebApp1-1.0.0-SNAPSHOT.war'
                    def appName = 'Redbus'

                    withCredentials([usernamePassword(credentialsId: 'Tomcat', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                        sh """
                        curl -u $USERNAME:$PASSWORD -T $warFile "$server/manager/text/deploy?path=/$appName&update=true"
                        """
                    }
                }
            }
        }
    }
}
