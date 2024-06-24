@Library("jhc-libs") _

pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
               git branch: 'main', url: 'https://github.com/Darkmatter85/jenkins.git'
            }
        }
        stage('Maven Build') {
            steps {
               sh 'mvn clean package'
            }
        }
        
        stage('Dev Deploy') {
            steps {
                tomcatDeploy("ec2-user","172.31.14.193","tomcat-dev","lms")
            }
        }
        
    }
}
