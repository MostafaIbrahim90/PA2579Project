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
        sh 'pip3 install pyvirtualdisplay'
        sh 'pip3 install webdriver-manager'
        sh 'python3 Demo/main.py'
      }
    }
  }
}
