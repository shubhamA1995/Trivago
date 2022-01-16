pipeline {

        options {
            buildDiscarder(logRotator(numToKeepStr: '5', artifactNumToKeepStr: '5'))
        }
        agent {label 'my_jenkins_node'}

        tools {
            maven 'Maven'
        }

        stages {
            stage('Code Compilation') {
                steps {
                    sh 'mvn clean compile'
                }
            }
              stage('QA Execution') {
                steps {
                    sh 'mvn clean test'
                }
            }
            stage('Code Package') {
                steps {
                    sh 'mvn clean package'
                }
            }
    }
	}