pipeline {
  agent none
  stages {
    stage('Smoke-ar') {
      parallel {
        stage('Smoke-ar') {
          steps {
            build 'Smoke-Tests-AR'
          }
        }
        stage('Smoke-cl') {
          steps {
            build 'Smoke-Tests-CL'
          }
        }
        stage('Smoke-co') {
          steps {
            build 'Smoke-Tests-CO'
          }
        }
      }
    }
    stage('Smoke-Report') {
      steps {
        sleep 1
      }
    }
    stage('HC-ar') {
      parallel {
        stage('HC-ar') {
          steps {
            build 'Healthcheck-Tests-AR'
          }
        }
        stage('HC-cl') {
          steps {
            build 'Healthcheck-Tests-CL'
          }
        }
        stage('HC-co') {
          steps {
            build 'Healthcheck-Tests-CO'
          }
        }
      }
    }
    stage('HC-Report') {
      steps {
        sleep 2
      }
    }
  }
}