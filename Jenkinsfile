pipeline {
    agent any
    environment{
        tomcat_ip = "172.31.42.250"
        tomcat_user = "ec2-user"
        deploy_folder = "/opt/tomcat10/webapps/"
    }

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Tangala123/Devops-7am.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('deploy'){
            steps{
              sshagent(['tomcat-deploy']) {
              sh "scp -o StrictHostKeyChecking=no target/*.war $tomcat_user@$tomcat_ip:$deploy_folder"
              sh "ssh $tomcat_user@$tomcat_ip /opt/tomcat10/bin/shutdown.sh"
              sh "ssh $tomcat_user@$tomcat_ip /opt/tomcat10/bin/startup.sh"
              }  
            }
        }
    }
}
