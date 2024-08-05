pipeline {
    agent any
	 tools
    {
       maven "Maven"
    }
    
    
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
		stage('Test') {
            steps {
                sh 'mvn clean test'
            }
        }
		stage('SonarScan') {
            steps {
                sh 'echo "SonarScan"'
            }
        }
        stage('Deploy') {
            steps {
        
		sh '''
		scp target/DevOpsWebApp1-1.0.0-SNAPSHOT.war root@54.254.215.34:/opt/apache-tomcat-9.0.91/webapps
#scp target/DevOpsWebApp1-1.0.0-SNAPSHOT.war root@54.254.215.34:/opt/apache-tomcat-9.0.91/webapps
'''
            }
        }
    }
}
