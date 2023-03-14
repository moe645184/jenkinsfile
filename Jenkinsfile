pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
              echo 'build start'
              withAnt(installation: 'ant') {
                  dir("/") {
                      sh "ant we"
                  }
              }
              echo 'build end'
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
