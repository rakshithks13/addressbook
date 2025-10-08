pipeline {
    agent any

    stages {
        stage('job') {
            steps {
                echo 'Building the first pipeline job'
                git 'https://github.com/rakshithks13/addressbook.git'
            }
        }
            stage('Build') {
            steps {
                echo 'Build'
                sh '''mvn compile
'''
            }
            }
            stage('Test') {
            steps {
                echo 'Test'
                sh '''mvn test
'''
            }
        }
        stage('Install') {
            steps {
                echo 'Install'
                sh '''mvn clean install
'''
        archiveArtifacts artifacts: 'Dockerfile', followSymlinks: false
            }
            }
        
    }
}
