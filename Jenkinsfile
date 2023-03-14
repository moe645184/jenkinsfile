pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
              withAnt(installation: 'default') {
                  dir("/") {
                    sh "ant we"
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
