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
    stage ('Install prerequiteies') {
        sh "yum -y install ncurses-devel"
    }
    stage('Build') {
      steps {
	sh "cd ${WORKSPACE}/vim;\
	make"
      }
    }
    stage('Run Tests') {
      steps {
	sh "cd ${WORKSPACE}/vim;\
	make test"
      }
    }
  }
  post {
      always {
        cleanWs()
          
      }
  }
}


