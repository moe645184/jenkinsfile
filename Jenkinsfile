pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                ant target: 'example', buildFile: 'build.xml'
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
