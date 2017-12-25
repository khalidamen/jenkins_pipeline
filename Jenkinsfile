pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
				npm install
                echo 'Building..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
