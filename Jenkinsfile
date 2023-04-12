pipeline {
  agent any 
  environment {
    NEW_VERSION = '1.0.0'
  }
  stages {
    stage("build") {
      when {
        expression {
        BRANCH_NAME== "main"
        }
      }
      steps {
        echo 'building the application ${NEW_VERSION} 1...'
        echo "building the application ${NEW_VERSION} 2..."
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
