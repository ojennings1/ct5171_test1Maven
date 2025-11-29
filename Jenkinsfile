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
                sh "mvn clean compile"
            }
        }

        stage('Test') {
            steps {
                sh "mvn test"
            }
        }

        stage('Package') {
            steps {
                sh "mvn package"
            }
        }

        stage('Run') {
            steps {
                sh "mvn exec:java"
            }
        }
    }

    post {
        success {
            // Archive the JAR so Jenkins stores it as a build artifact
            archiveArtifacts allowEmptyArchive: true,
                             artifacts: '**/ct5171_test1Maven.jar'
        }
    }
}
