pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages {
        stage('git checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Neeraj-2806/Nexus-Demo.git'
            }
        }
        stage('mvn compile') {
            steps {
                sh "mvn compile"
            }
        }
         stage('mvn test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('build the code') {
            steps {
                sh 'mvn package'
            }
        }
         stage('deploy the artifact') {
            steps {
                withMaven(globalMavenSettingsConfig: 'settings.xml', jdk: 'jdk17', maven: 'maven3', mavenSettingsConfig: '', traceability: true){
                    sh 'mvn deploy'
                }
            }
        }
    }
}
