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
        always {
            sh 'echo "pipeline complete"'
        }
    }
}
