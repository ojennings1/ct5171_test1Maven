pipeline {
    agent any

    stages {
        stage('GetProject') {
            steps {
                git 'https://github.com/ojennings1/ct5171_test1Maven.git'
            }
        }
        stage('Build') {
            steps {
                sh "mvn clean package"
            }
        }
        stage('Run') {
            steps {
                sh "mvn exec:java"
            }
        }
    }
}