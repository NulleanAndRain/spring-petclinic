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
                bat "D:\\tmp\\_apache-maven-3.8.4\\bin\\mvn.cmd -Dbuild_version=" + env.BUILD_NUMBER.toString() + " package"
            }
        }

        stage('Publish') {
            steps {
                bat "move /Y \"${workspace}\\target\\jenkins-sample-*\" C:\\Users\\Алексей\\Downloads"
            }
        }
    }
}
