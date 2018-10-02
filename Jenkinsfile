pipeline {
  agent any

  stages {
    stage('build-poi') {
      when { branch 'backend/api-poi' }
      steps {
        sh "cd src/apis/poi && /bin/bash ./build.sh"
      }
    }

    stage('cd trips') {
      when { branch 'backend/api-trips' }
      steps {
        sh "cd src/apis/trips && /bin/bash ./build.sh"
      }
    }

  }
}

