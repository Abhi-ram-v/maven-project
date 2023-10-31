pipeline {
    agent any
    tools {
        maven "maven3"
    }
    stages {
        stage('SCM') {
            steps {
                git branch: 'master', credentialsId: 'github-integration', url: 'https://github.com/Abhi-ram-v/maven-project.git'
            }
        }
        stage('Build') {
            steps {
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

            }
        }
        stage('Artifacts') {
            steps {
                archiveArtifacts 'target/*.jar'
            }
        }
    }
}
