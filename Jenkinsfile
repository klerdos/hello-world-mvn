node {
    try {
        stage('git clone') {
            checkout scm
        }
        stage('Validate') {
            echo 'Validate..'
            withMaven (maven: 'maven-3.9.8'){
              sh 'mvn compile'
            }
        }
        stage('Build') {
            echo 'Building..'
            withMaven (maven: 'maven-3.9.8'){
              sh 'mvn verify'
            }
        }
        stage('Test') {
            echo 'Testing..'
            withMaven (maven: 'maven-3.9.8'){
                sh 'mvn test'
            }
        }
    } finally {
    }
}
