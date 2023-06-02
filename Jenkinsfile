pipeline {
  agent any
  options {
        // This is required if you want to clean before build
        skipDefaultCheckout(true)
    }
  stages {
    stage('Clean') {
            steps {
                // Clean before build
                cleanWs()
            }
    }
    stage('version') {
      steps {
        sh 'python3 --version'
      }
    }
    stage('Unit Testing') {
      steps {
          sh 'pip3 install pytest'
          sh 'pytest unittest/'
      }
    }
    stage('System Testing') {
      steps {
        sh 'pip install -r requirements.txt'
        sh 'pip3 install selenium'
        sh 'pip3 install webdriver-manager'
        sh 'python3 Demo/main.py'
      }
    }
  }
  post {
        // Clean after build
        always {
            cleanWs(cleanWhenNotBuilt: false,
                    deleteDirs: true,
                    disableDeferredWipeout: true,
                    notFailBuild: true,
                    patterns: [[pattern: '.gitignore', type: 'INCLUDE'],
                               [pattern: '.propsfile', type: 'EXCLUDE']])
        }
    }
}

