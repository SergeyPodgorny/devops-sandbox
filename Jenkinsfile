pipeline {
    agent { docker { image 'gradle:latest' } }
    stages {
        stage('application build') {
            steps {
                sh '''
                cd project
                gradle build
                '''
            }
        }
        stage('docker image build'){
            steps {
            sh '''
            pwd
            '''
            }

        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}