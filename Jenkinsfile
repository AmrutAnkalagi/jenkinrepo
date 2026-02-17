pipeline {
    agent any
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    triggers {
        pollSCM('* * * * *')
    }
    tools {
        maven 'MAVEN_3.9.12'
    }
    stages {
        stage('SCM') {
            steps {
                git url 'https://github.com/AmrutAnkalagi/jenkinrepo.git'
                branch 'main'
            }              
        }
        stage ('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

    }
}