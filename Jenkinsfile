pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                gradlew('build')
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
