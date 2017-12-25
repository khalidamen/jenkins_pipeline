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
				sh 'npm version patch'
				sshagent (credentials: ['moby_github']) {
					sh 'git add . && git commit -m \'bumped patch version\''
					sh 'git push origin'
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
