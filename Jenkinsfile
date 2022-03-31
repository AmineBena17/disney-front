pipeline {
  agent any

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
  }
}