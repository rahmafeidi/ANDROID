pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo "building"
        sleep 10
      } 
    }
    stage('Test') {
      steps {
        sh './gradlew task'
      }
    }
    stage('Deploy') {
      steps {
        echo "deploying"
        sh ' export ANDROID_HOME=/home/ubuntu/Android/Sdk'
  
        ./gradlew assembleDebug 
        ./gradlew installDebug 
      }
    }
  }
}
