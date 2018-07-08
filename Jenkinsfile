#!/usr/bin/env groovy

pipeline {
    agent any
    tools{
           maven 'MavenGlobalToolConfig'
        }
    stages {
        stage('Stage clean') {
            steps {
                echo 'cleaning...'
                sh 'mvn clean'
            }
        }
        stage('Stage package') {
            steps {
               echo 'packaging.....'
               sh 'mvn package'
            }
        }
    }
}