pipeline {
  agent any

  environment {
    DEMO='1.1'
  }

  stages {
    stage('stage-1') {
      echo "This is build number $BUILD_NUMBER of demo $DEMO"
    }
  }
}