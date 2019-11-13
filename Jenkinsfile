pipeline {
    agent any

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
        stage('Run') {
            steps {
                echo 'Running....'
                when {
                  expression {
                    currentBuild.result == null || currentBuild.result == 'SUCCESS' 
                  }
                }
                steps {
                  sh 'java -jar target/*.jar'
                }
            }
        }
    }
}