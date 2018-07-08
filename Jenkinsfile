#!/usr/bin/env groovy

pipeline {
    agent any
    tools{
           maven 'MavenGlobalToolConfig'
        }
    stages {
        stage('Stage - Build') {
            steps {
                echo 'cleaning and packaging.....'
                sh 'mvn clean package -Dmaven.test.skip=true'
            }
        }
        stage('Stage - Deploy') {
            steps {
                sh 'scp -v -o StrictHostKeyChecking=no  -i /var/lib/jenkins/secrets/ubuntu-jenkins.pem target/*.jar ubuntu@13.232.153.38:/home/ubuntu'
                sh "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/secrets/ubuntu-jenkins.pem ubuntu@13.232.153.38 '/home/ubuntu/startup.sh'"
            }
        }
    }
}