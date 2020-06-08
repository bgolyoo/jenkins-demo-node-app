pipeline {
  agent {
    docker {
      image 'node:12'
    }
  }

  environment {
    DEMO='1.1'
  }

  stages {
    stage('only merge request') {
      when {
        changeRequest()
      }
      steps {
        echo 'only merge request'
      }
    }
    stage('only tag push') {
      when {
        buildingTag()
      }
      steps {
        echo 'only tag push'
      }
    }
    stage('versions') {
      steps {
        echo "This is build number $BUILD_NUMBER of demo $DEMO"
        sh 'node -v'
        sh 'npm -v'
      }
    }
    stage('npm install') {
      steps {
        sh 'npm i'
      }
    }
    stage('test') {
      steps {
        sh 'npm test'
      }
    }
  }
}
