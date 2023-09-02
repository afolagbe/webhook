pipeline {
    agent any
    tools {
        jdk 'jdk'
        maven 'maven'
    }
    stages{
        stage('PULL CODE FROM GITHUB'){
            steps{
                git branch: 'ci-jenkins', url: 'https://github.com/afolagbe/Batch3-project-.git'
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
        stage('QUALITY GATES'){
            steps{
                timeout(time:1 unit: 'MINUTES'){
                    waitForQualityGate aboutPipeline: true
                }
            }
        }
    }
}