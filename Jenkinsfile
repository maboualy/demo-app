pipeline {
  agent any 
  stages {
    stage("build") {
      steps {
      echo 'building the application..'
      }
    }
    stage("test"){
      steps {
        echo 'testing the application..'
      }
    }
    stage("deploy"){
      steps {
      echo 'deploying the application..'
      }
    }
  }
  post {
    always {
      echo 'always'
    }
    success {
      echo 'success'
    }
    failure {
    echo 'failure'
    }
  }
}
