pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                ant(installation: 'default'){
                  dir("/") {
                    if (isUnix()) {
                      sh "we"
                    } else {
                      bat "we"
                    }
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
