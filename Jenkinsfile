pipeline {
  agent {
    node {
      label 'slave-label'
    }

  }
  stages {
    stage('git') {
      steps {
        git 'https://github.com/moaaz71/moaaz.git'
      }
    }

  }
}