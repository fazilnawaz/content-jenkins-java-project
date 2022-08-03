pipeline {
  agent none

  environment {
    MAJOR_VERSION = 1
  }

  stages {
    
    stage('Git Information') {
      agent any

      steps {
        echo "My Branch Name: ${env.BRANCH_NAME}"
      }
    }
    
    stage('Checkout') {
      steps {
        //    sleep 60
        step([$class: 'WsCleanup'])
        checkout([$class: 'GitSCM', branches: [
          [name: '$BRANCH_NAME']
        ], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [
          [credentialsId: '', url: '$GIT_URL']
        ]])
      }
    }
  }
}
