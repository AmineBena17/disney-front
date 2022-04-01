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

    stage('Test') {
                steps {
                    sh "chmod +x -R ./jenkins/scripts/test.sh"
                    sh './jenkins/scripts/test.sh'
                }
            }
  }

  stage('Deploy'){
        if(env.BRANCH_NAME == 'master'){
          sh 'docker build -t react-app --no-cache .'
          sh 'docker tag react-app localhost:5000/react-app'
          sh 'docker push localhost:5000/react-app'
          sh 'docker rmi -f react-app localhost:5000/react-app'
        }
}