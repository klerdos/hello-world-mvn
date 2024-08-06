node('builtin') {
    stage('git clone') {
        checkout scm
    }
    stage('Validate') {
        echo 'Validate..'
        withMaven (maven: '3.9.8'){
          sh 'mvn compile'
        }
    }
    stage('Build') {
        echo 'Building..'
        withMaven (maven: '3.9.8'){
          sh 'mvn build'
        }
    }
    stage('Test') {
        echo 'Testing..'
        withMaven (maven: '3.9.8'){
            sh 'mvn test'
        }
    }
}
