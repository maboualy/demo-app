def dv
pipeline {
  agent any 
  tools {
    maven 'maven'
  
  }
  environment {
    NEW_VERSION = '1.0.0'
    SERVER_CREDENTIAL = credentials('some_credential')
  }
  stages {
    stage("init"){
      steps{
      script {
      dv = load 'script.groovy'
      }}
    }
    stage("build") {
      when {
        expression {
        BRANCH_NAME== "main"
        }
      }
      steps {
        script {
        
          dv.build()
        }
         echo 'building the application ${NEW_VERSION} 1...'
         
        echo "building the application ${NEW_VERSION} 2..."
        withCredentials([usernamePassword(credentialsId: 'some_credential', usernameVariable:'USER', passwordVariable:'PWD')]){
          sh 'echo building the application ${USER} ${PWD} 3...'
        }
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
