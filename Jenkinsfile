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
        stage('Install Chrom Browser'){
            steps{
                sh '''#!/bin/bash
                    google-chrome --version
                    if [ "$?" = 1 ]
                    then
                    wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
                    sudo add-apt-repository "deb http://dl.google.com/linux/chrome/deb/ stable main"
                    sudo apt update
                    sudo apt install google-chrome-stable -y
                    google-chrome --version
                    else
                    echo "Chrome Already Installed"
                    fi
                    
                '''
            }
        }
    }
}
