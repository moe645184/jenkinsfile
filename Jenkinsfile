pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                withAnt(installation: 'default') {
                  ant(target: 'example', buildFile: 'build.xml')
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}