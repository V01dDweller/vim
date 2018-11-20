#!groovy
pipeline {
  agent any
  stages {
    stage('Checkout: Code') {
      steps {
	sh "git clone https://github.com/V01dDweller/vim.git"
      }
    }
    stage('Build') {
      steps {
	sh "cd /var/lib/jenkins/workspace/Vim2/vim;\
	make"
      }
    }
  }
  post {
    always {
      cleanWs()
    }
  }
}


