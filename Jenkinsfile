node('builtin') {
    stage('Validate') {
        echo 'Validate..'
        withMaven {
          sh 'mvn compile'
        }
    }
    stage('Build') {
        echo 'Building..'
        withMaven {
          sh 'mvn build'
        }
    }
    stage('Test') {
        echo 'Testing..'
        withMaven {
            sh 'mvn test'
        }
    }
}
