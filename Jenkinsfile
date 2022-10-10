pipeline {
	agent any
	 stages {
        stage('Checkout') { 
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-user', url: 'https://github.com/devopsdeepdive/maven-web-project.git']]]) 
            }
        }
	stage('Compile') { 
            steps {
              sh 'mvn compile'
            }
        }
	stage('Test') { 
            steps {
              sh 'mvn test'
              sleep 300
            }
        }
	stage('Package') { 
            steps {
              sh 'mvn package'
            }
        }
	}
}
