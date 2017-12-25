pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
				deleteDir()
				sh 'npm version patch'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
