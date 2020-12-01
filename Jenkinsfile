pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                gradlew('clean', 'build')
            }
        }

        stage('Test') {
            steps {
                gradlew('test')
            }
            post {
                always {
                    junit '**/build/test-results/test/TEST-*.xml'
                }
            }
        }
    }
}
