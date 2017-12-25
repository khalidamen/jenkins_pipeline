pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
				sh 'npm version patch'
				sh 'git commit -m \'bumped version\''
				sh 'git push origin'
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
