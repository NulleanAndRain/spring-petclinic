pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat "build.bat"
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