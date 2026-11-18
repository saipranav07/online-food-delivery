
node {

    // STAGE 1: CHECKOUT
    stage('Checkout') {

        checkout scm

        echo 'Source code downloaded successfully'
    }

    // STAGE 2: BUILD
    stage('Build') {

        bat 'mvn clean compile'
    }

    // STAGE 3: TEST
    stage('Test') {

        bat 'mvn test'
    }

    // STAGE 4: PACKAGE
    stage('Package') {

        bat 'mvn package -DskipTests'
    }

    // STAGE 5: ARCHIVE
    stage('Archive') {

        archiveArtifacts artifacts: '**/target/*.war',
                         fingerprint: true
    }

}
