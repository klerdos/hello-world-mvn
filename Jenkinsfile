node('builtin') {
    stage('Validate') {
        echo 'Validate..'
        sh 'mvn compile'
    }
    stage('Build') {
        echo 'Building..'
        sh 'mvn build'
    }
    stage('Test') {
        echo 'Testing..'
        sh 'mvn test'
    }
}
