pipeline {
    agent any

    stages {
        stage('Setup') {
            steps {
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './stop.sh'
            }
        }
        stage('Deploy') {
            steps {
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './slowDeploy.sh'
            }
        }
    }
    post {
        success {
            sh 'echo "pipeline complete"'
            sh "chmod +x -R ${env.WORKSPACE}"
            sh './stop.sh'
        }
        failure  {
            sh 'echo "All services is left running. Come and check me out or make a new run."'
        }
    }
}
