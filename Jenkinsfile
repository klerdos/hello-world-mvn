pipeline {
    agent { label 'builtin' }

    stages {
        stage('Validate') {
            steps {
                echo 'Validate..'
                sh 'mvn compile'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'mvn build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
            }
        }
    }
}
