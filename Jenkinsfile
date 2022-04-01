node {
  try {
  agent any
    stage('Checkout') {
      checkout scm
    }
    stage('Environment') {
      sh 'git --version'
      echo "Branch: ${env.BRANCH_NAME}"
      sh 'docker -v'
      sh 'printenv'
    }
    stage('Deploy'){
      if(env.BRANCH_NAME == 'master'){
        sh 'docker build -t disney-front --no-cache .'
        sh 'docker tag disney-front localhost:5000/disney-front'
        sh 'docker push localhost:5000/disney-front'
        sh 'docker rmi -f disney-front localhost:5000/disney-front'
      }
    }
  }
  catch (err) {
    throw err
  }
}