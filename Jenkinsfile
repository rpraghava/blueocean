pipeline {
  agent {
    docker 'maven:3.3.3'
  }
  stages {
    stage('build') {
      steps {
        sh '''pipeline {
    agent { docker \'maven:3.3.3\' }
    stages {
        stage(\'build\') {
            steps {
                sh \'mvn --version\'
            }
        }
    }
}'''
        }
      }
      stage('Test') {
        steps {
          sh '''pipeline {
    agent { docker \'node:6.3\' }
    stages {
        stage(\'build\') {
            steps {
                sh \'npm --version\'
            }
        }
    }
}'''
          }
        }
        stage('STG') {
          steps {
            sh '''pipeline {
    agent { docker \'ruby\' }
    stages {
        stage(\'build\') {
            steps {
                sh \'ruby --version\'
            }
        }
    }
}'''
            }
          }
        }
      }