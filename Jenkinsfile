pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
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
