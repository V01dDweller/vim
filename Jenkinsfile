#!groovy
pipeline {
  agent any
  options {
    timestamps()
    skipStagesAfterUnstable()
  }
  stages {
    stage('Checkout: Code') {
      options {
        retry(3)
      }
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
	make test"
      }
    }
  }
}


