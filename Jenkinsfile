#!groovy
pipeline {
  agent any
  options {
    retry(3)
    timestamps()
    skipStagesAfterUnstable()
  }
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
    stage('Run Tests') {
      steps {
	sh "cd /var/lib/jenkins/workspace/Vim2/vim;\
	make check"
      }
    }
  }
  post {
    always {
      cleanWs()
    }
  }
}


