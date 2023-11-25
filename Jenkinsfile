pipeline {
    agent {
        label "jenkins-agent"
    }
    tools {
        jdk "Java17"
        maven "Maven3"
    }
    stages{
        stage('Cleanup Workspace') {
            steps {
                cleanWs()
            }
        }
        stage('Checkout From SCM') {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/krishnamsg/complete-prodcution-e2e-pipeline.git'
            }
        }
                stage('Build Application') {
            steps {
                sh "mvn clean install"
            }
        }
        stage('Test Application') {
            steps {
                sh 'mvn test'
            }
        }

    }
}