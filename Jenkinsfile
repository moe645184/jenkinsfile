pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                withAnt(jdk: 'Java11', ant: 'ANT_HOME') {
                    sh 'ant -f build.xml clean compile'
                }
            }
        }
        stage('Test') {
            steps {
                withAnt(jdk: 'Java11', ant: 'ANT_HOME') {
                    sh 'ant -f build.xml test'
                }
            }
        }
        stage('Deploy') {
            steps {
                withAnt(jdk: 'Java11', ant: 'ANT_HOME') {
                    sh 'ant -f build.xml deploy'
                }
            }
        }
    }
}
