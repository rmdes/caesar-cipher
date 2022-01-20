pipeline {
    agent any

    stages {
        stage('GitHub Auth') {
            steps {
                echo 'Building..'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'e7ff015a-07d8-4a56-ae61-9c58fa2ad826', url: 'git@github.com:rmdes/caesar-cipher.git']]])
            }
        }
        stage('Test') {
            steps {
                echo 'Test the test'
		sh './gradlew tasks --all'
            }
        }
        stage('Build') {
            steps {
                echo 'Build the Jar artifact'
		sh './gradlew clean build'
            }
        }
	stage ('Release to Github') {
	    steps {
	        sh ''
           }
}
        }
    }

