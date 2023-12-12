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

    stage('build ') {
      steps {
        sh 'mvn compile test package install '
      }
    }

    stage('Docker image') {
      steps {
        sh '''cd /home/moaaz/jenkins_home/workspace/moaaz_master
docker build -t java:v1 .
'''
      }
    }

    stage('deploy container') {
      steps {
        sh 'docker run -it -d -p 8080:9090 --name=java-app java:v1'
      }
    }

    stage('error') {
      steps {
        echo 'Deployment Done'
      }
    }

  }
}