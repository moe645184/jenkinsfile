pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                ant{
                  dir("/") {
                      sh "we"
                  }
                }
            }
        }
        stage('Test') {
            steps {
                sh 'make check'
                junit 'reports/**/*.xml'
            }
        }
        stage('Deploy') {
            steps {
                sh 'make deploy'
            }
        }
    }
}
