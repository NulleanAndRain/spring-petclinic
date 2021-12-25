pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat "build.bat"
            }
        }
        stage('Archive'){
            steps{
                bat 'rar.bat'
            }
        }
        stage('Publish'){
            steps{
                bat 'derar.bat'
            }
        }
    }
}