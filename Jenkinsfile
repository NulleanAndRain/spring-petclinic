pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat "C:\Users\Алексей\Downloads\_apache-maven-3.8.4\bin\mvn.cmd package"
            }
        }

        stage('Archive') {
            steps {
                script {
                    zip zipFile: env.BUILD_NUMBER.toString() + '.zip', dir: 'Test/bin/Release'
                }
            }
        }

        stage('Unarchive') {
            steps {
                unzip zipFile: env.BUILD_NUMBER.toString() + '.zip', dir: 'G:\\deploy\\' + env.BUILD_NUMBER.toString()
            }
        }
    }
}
