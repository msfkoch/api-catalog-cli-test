pipeline {
  agent any
  environment {
    ANYPOINT_ORG_ID = 'e8f30ff9-0223-4e40-8b59-c67433a7e996'
  }
  stages {
    stage('Checkout Scm') {
      steps {
        git(branch: 'main', url: 'https://github.com/msfkoch/api-catalog-cli-test.git')
      }
    }
    stage('Publish API') {
      steps {
        withCredentials([
          usernamePassword(usernameVariable: 'ANYPOINT_USERNAME',
          passwordVariable: 'ANYPOINT_PASSWORD',
          credentialsId: 'my-anypoint-creds')]
        ) {
          sh '''api-catalog publish-asset --organization $ANYPOINT_ORG_ID'''
        }
      }
    }
  }
}
