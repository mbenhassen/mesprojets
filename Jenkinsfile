pipeline {
    agent any
    stages {
        stage('Pull') {
            steps {
                checkout([$class: 'GitSCM',
                branches: [[name: '*/master']],
                doGenerateSubmoduleConfigurations: false,
                extensions: [],
                submoduleCfg: [],
                userRemoteConfigs: [[url: 'https://github.com/mbenhassen/mesprojets.git']]])
                sh "ls"
            }
        }
        stage('Build') {
            steps {
                sh "javac Main.java"
            }
        }
        stage('Run') {
            steps {
                sh "java Main"
            }
        }
    }
}