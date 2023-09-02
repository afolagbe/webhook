pipeline {
    agent any
    tools {
        jdk 'JDK'
        maven 'maven'
    }
    stages{
        stage('PULL CODE FROM GITHUB'){
            steps{
                git branch: 'webapp', url: 'https://github.com/afolagbe/webhook.git'
            }
        }
        stage('BUILD THE CODE'){
            steps{
                sh 'mvn install -DskipTest'
            }
        }
        stage('TEST'){
            steps{
                sh 'mvn verify -DskipTest'
            }
        }
        stage('INTEGRATION TEST'){
            steps{
                sh 'mvn verify -DskipTest'
            }
        }
        stage('UNIT TEST'){
            steps{
                sh 'mvn verify test'
            }
        }
    }
}