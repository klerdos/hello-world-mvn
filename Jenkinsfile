pipeline {
    agent { label 'builtin' }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'mvn package'
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
    }
}
