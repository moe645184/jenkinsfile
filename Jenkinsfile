pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
              withAnt(installation: 'ant') {
                  dir("/") {
                    if (isUnix()) {
                      sh "ant we"
                    } else {
                      bat "ant we"
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
