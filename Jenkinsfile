pipeline {
    agent any
    stages {
        stage('Stage clean') {
            steps {
                echo 'cleaning...'
                withMaven(maven : 'MavenGlobalToolConfig') {
                    sh "mvn clean"
                }

            }
        }
        stage('Stage package') {
            steps {
                echo 'packaging.....'
                withMaven(maven : 'MavenGlobalToolConfig') {
                    sh "mvn package"
                }
            }
        }
    }
}