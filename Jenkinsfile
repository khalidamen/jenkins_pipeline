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
				withCredentials([usernamePassword(credentialsId: 'moby_github', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
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
