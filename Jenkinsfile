
pipeline {
  agent any
  stages {
    stage('Git checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'CheckoutOption']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'gitaccess', url: 'https://github.com/vajohnvinodh/nodejs.git']]])
      }
    }
    stage('Building the image') {
      steps {
        sh """
        docker build -t "nodejsapplication" .
        """
      }
    }
  }
}
