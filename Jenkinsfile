pipeline {
  agent any
    environment {
      ANYPOINT_ORG_ID = '1234abc-b34a-7cd3-4s32-12345abc2345'
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
