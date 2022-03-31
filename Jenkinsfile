pipeline {

    agent {
        docker {
            image 'node:lts-buster-slim'
            args '-p 3000:3000'
        }

  tools {nodejs "NodeJS"}

  stages {

    stage('Git') {
      steps {
        git 'https://github.com/AmineBena17/disney-front.git'
      }
    }

    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
                steps {
                    sh './jenkins/scripts/test.sh'
                }
            }
  }