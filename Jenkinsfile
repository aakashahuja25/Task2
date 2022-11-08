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
        stage('Install Chrome Browser'){
            steps{
                sh '''#!/bin/bash
                    google-chrome --version
                    if [ "$?" -ne 0 ]
                    then
                    wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
                    sudo add-apt-repository "deb http://dl.google.com/linux/chrome/deb/ stable main"
                    sudo apt update
                    sudo apt install google-chrome-stable -y
                    google-chrome --version
                    else
                    echo "Chrome Already Installed Trying to upgrade to the latest Version !!"
                    sudo apt-get --only-upgrade install google-chrome-stable -y
                    fi
                    
                '''
            }
        }
        stage('Install Chrome driver'){
            steps{
                sh '''#!/bin/bash
                    chromedriver --version
                    if [ "$?" -ne 0 ]
                    then
                    version=$(curl -s "https://chromedriver.storage.googleapis.com/LATEST_RELEASE")
                    wget -qP /tmp/ "https://chromedriver.storage.googleapis.com/${version}/chromedriver_linux64.zip"
                    sudo unzip -o /tmp/chromedriver_linux64.zip -d /usr/bin
                    chromedriver --version
                    else
                    echo "ChromeDriver Already Installed"
                    fi
                    
                '''
            }
        }
    }
}
