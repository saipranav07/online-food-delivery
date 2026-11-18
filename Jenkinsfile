
node {

    stage('Checkout') {
        echo 'Source code checked out from GitHub'
    }

    stage('Build') {
        bat 'mvn clean compile'
    }

    stage('Test') {
        bat 'mvn test'
    }

    stage('Package') {
        bat 'mvn package -DskipTests'
    }

    stage('Archive') {
        archiveArtifacts artifacts: '**/target/*.war',
                         fingerprint: true
    }

}
