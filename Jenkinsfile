pipeline {
    agent any


    stages {
	
		stage('Checkout'){
			steps {
				deleteDir()
				checkout scm
			}
		}
        stage('Build') {
            steps {
				sh 'git tag'
				sh 'npm version patch'
				withCredentials([SSHUserPrivateKeyBinding(credentialsId: 'moby_github')]) {
					sh 'git push origin master'
					sh 'git push --tags'
				}
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
