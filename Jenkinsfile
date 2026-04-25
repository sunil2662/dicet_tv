pipeline {
    agent {label 'dev'}
    tools {maven 'maven'}
    stages {
        stage('Git') {
            steps {
                git 'https://github.com/sunil2662/dicet_tv.git'
            }
        }
        stage('maven'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('deploy'){
            steps{
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://3.108.42.226:8080/')], contextPath: 'sunil', war: '**/*.war'
            }
        }
    }
}
