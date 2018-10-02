pipeline {
  agent any

  stages {
    stage('build-poi') {
      when { branch 'backend/api-poi' }
      steps {
        sh "cd src/apis/poi && ./build.sh"
      }
    }

    stage('cd trips') {
      when { branch 'backend/api-trips' }
      steps {
        sh "cd src/apis/trips && ./build.sh"
      }
    }

  }
}

