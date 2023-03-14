pipeline {
    agent any
    tools{
        ant 'Ant'
    }
    stages {
        stage('Build') {
            steps {
                withAnt{
                    sh '''
                    pwd
                    ls
                    ant we
                    '''
                }
            }
        }
    }
}
