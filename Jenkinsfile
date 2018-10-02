pipeline {
  agent any

  stages {
    stage('build-poi') {
      when { branch 'backend/api-poi' }
      steps {
        withCredentials([azureServicePrincipal('credentials_id')]) {
            sh 'az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID'
            sh "cd src/apis/poi && /bin/bash -x build.sh -b Debug -r openhackgpx5rg -t api-poi -s ../../../.. -d example.com -n coffee -g openhackgpx5acr"
        }
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

