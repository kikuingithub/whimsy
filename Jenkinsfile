pipeline {
  agent {
    docker {
      image 'maven'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        sh 'ls -lh'
      }
    }
    stage('Browser Tests') {
      steps {
        parallel(
          "Firefox": {
            sh 'echo \'setting up selenium environment\''
            sh 'ping -c 5 localhost'
            
          },
          "Safari": {
            sh 'echo \'setting up selenium environment\''
            sh 'ping -c 8 localhost'
            
          },
          "Chrome": {
            sh 'echo \'setting up selenium environment\''
            sh 'ping -c 3 localhost'
            
          },
          "Internet Explorer": {
            sh 'echo \'setting up selenium environment\''
            sh 'ping -c 4 localhost'
            
          }
        )
      }
    }
    stage('Static Analysis') {
      steps {
        sh 'ls -l'
      }
    }
    stage('Deploy') {
      steps {
        sh 'ls -lh'
      }
    }
  }
  environment {
    DEBUG = 'true'
  }
}
