pipeline {
    /*
    agent {
        docker {
            image 'openjdk:11'
            args  '-v /tmp:/tmp'
            reuseNode true
        }
    }
    */
    agent any

    stages {
        stage('Build') {
            steps {
                sh './gradle clean build'
            }
        }

        stage('Test') {
            steps {
                sh './gradle test'
            }
            post {
                always {
                    archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
                    junit '**/build/test-results/test/TEST-*.xml'
                }
            }
        }
    }
}
