pipeline {
    agent any

	deleteDir()

    stages {

		stage('Checkout') {
	      checkout scm
    	}

        stage('Build') {
            steps {
				sh 'git tag'
				sh 'npm version patch'
				sh 'git push origin master'
				sh 'git push --tags'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
