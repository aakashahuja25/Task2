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
        stage('Install Chrom Browser')
            steps{
                sh 'wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -'
                sh 'sudo add-apt-repository "deb http://dl.google.com/linux/chrome/deb/ stable main"'
                sh 'sudo apt update'
                sh 'sudo apt install google-chrome-stable -y'
                sh 'google-chrome --version'
            }
    }
}
