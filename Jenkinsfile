pipeline {
  agent any
  stages {
    stage('version') {
      steps {
        sh 'python3 --version'
      }
    }
    stage('SystemTesting') {
      steps {
        sh 'pip install -r requirements.txt'
        sh 'pip3 install selenium'
        sh 'wget https://chromedriver.storage.googleapis.com/72.0.3626.69/chromedriver_linux64.zip'
        sh 'unzip chromedriver_linux64.zip'
        sh 'sudo mv chromedriver /usr/local/bin/ -S M@tr!x1990'
        sh 'hmod +x /usr/local/bin/chromedriver'
        sh 'pip3 install webdriver-manager'
        sh 'python3 Demo/main.py'
      }
    }
  }
}
