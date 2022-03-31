pipeline {
  agent any

  tools {nodejs "mvn-3.8.5"}

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
                    sh "chmod +x -R ./jenkins/scripts/test.sh"
                    sh './jenkins/scripts/test.sh'
                }
            }
  }
}