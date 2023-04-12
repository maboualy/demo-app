pipeline {
  agent any 
  stages {
    stage("build") {
      when {
        expression {
        BRANCH_NAME== "main"
        }
      }
      steps {
      echo 'building the application..'
      }
    }
    stage("test"){
      when {
        expression {
          BRANCH_NAME == "dev"
        }
      }
      steps {
        echo 'testing the application..'
      }
    }
    stage("deploy"){
      when {
        expression {
        BRANCH_NAME == "main"
        }
      }
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
