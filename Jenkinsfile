pipeline {
  agent any

  stages {
    stage('cd poi') {
      when { branch 'backend/api-poi' }
      steps {
        sh "cd src/apis/poi"
      }
    }

    stage('cd trips') {
      when { branch 'backend/api-trips' }
      steps {
        sh "cd src/apis/trips"
      }
    }

    stage('Build') {
      steps {
        sh "./build.sh"
      }
    }
  }
}

