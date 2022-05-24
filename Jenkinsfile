pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git(branch: '*main', url: 'https://github.com/msfkoch/api-catalog-cli-test.git')
      }
    }

  }
}