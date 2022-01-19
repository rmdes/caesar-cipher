pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'e7ff015a-07d8-4a56-ae61-9c58fa2ad826', url: 'git@github.com:rmdes/caesar-cipher.git']]])
            }
        }
        stage('Test') {
            steps {
                echo 'Test the test'
		gradle tasks --all
            }
        }
        stage('Build') {
            steps {
                echo 'Build the Jar artifact'
		gradle build
            }
        }
    }
}
