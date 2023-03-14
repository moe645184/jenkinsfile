pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
              echo 'build start'
              withAnt(installation: 'Ant') {
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
