pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('git') {
      steps {
        git(url: 'https://github.com/shalant/flasking3.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t flask_app .'
      }
    }

    stage('Docker login') {
      steps {
        sh '''docker login -u dougrosenbergdev -p a1c8b9c4-ef65-4030-8e69-d90f13ab9795
'''
      }
    }

    stage('Docker push') {
      steps {
        sh 'docker push flask_app:latest'
      }
    }

  }
}