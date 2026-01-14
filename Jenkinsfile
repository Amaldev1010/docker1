pipeline {
  agent any

  stages{
   
    stage('Stop old contaioner'){
      steps{
        bat 'docker rm -f company-1website || exit 0'
      }
    }
   
    stage('checkout code') {
      steps {
        echo 'pulling code from github'
        checkout scm
      }
    }

    stage('build docker image'){
      steps{
        echo 'Building Docker Image'
        bat 'docker build -t company-1website .'
      }
    }
    stage('Run Docker container'){
      steps{
        echo 'Running Docker Container'
        bat 'docker run -d -p 8070:80 company-1website'
      }
    }
   
   
   
  }
}
