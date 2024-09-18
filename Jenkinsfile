node ("jenkins-jenkins-agent") {
    env.AWS_REGION = 'us-east-1'  // Tento údaj není kritický, protože MinIO není regionální
    env.AWS_ACCESS_KEY_ID = 'O25lWE1zlT3AhRuWQqWU'
    env.AWS_SECRET_ACCESS_KEY = 'SBbroI8BMe7HGCrefT6WcCVjXAk1TrFN4ZEYKKfy'
    env.MINIO_ENDPOINT = 'http://minio.minio:9000'  // Endpoint MinIO serveru
    env.S3_BUCKET = 'hello-world-mvn-bucket'

    try {
        stage('git clone') {
            checkout scm
        }
        // stage('download cache') {
        //     // Nastavení environmentální proměnné pro custom endpoint
        //     withEnv(["AWS_S3_ENDPOINT=${env.MINIO_ENDPOINT}"]) {
        //         s3Download(file: 'cache.tar.gz', bucket: "${env.S3_BUCKET}", path: 'cache.tar.gz')
        //         sh 'tar -xzvf cache.tar.gz -C ~/.m2/repository'
        //     }
        // }
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
        // stage('Upload cache') {
        //     sh 'tar -czvf cache.tar.gz -C ~/.m2/repository .'
        //     withEnv(["AWS_S3_ENDPOINT=${env.MINIO_ENDPOINT}"]) {
        //         s3Upload(file: 'cache.tar.gz', bucket: "${env.S3_BUCKET}")
        //     }
        // }
    } finally {
    }
}
