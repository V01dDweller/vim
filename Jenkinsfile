#!groovy
pipeline {
  agent any
  stages {
    stage('Checkout: Code')
    node {
      steps {
	sh "git clone https://github.com/V01dDweller/vim.git"
      }
    }
    stage('Build')
    node {
      steps {
	sh "cd /var/lib/jenkins/workspace/Vim/vim;\
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


