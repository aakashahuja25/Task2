pipeline{
    agent {
       label "jenkins-slave"
    }
    stages{
        stage('build'){
            steps{
                sh 'echo "Build Triggered from webhook"'
            }
        }
    }
}
