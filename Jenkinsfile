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
        sh ' export ANDROID_SDK_ROOT=/home/ubuntu/Android/Sdk'
        sh './gradlew clean '
        sh 'gradle wrapper  '
        sh 'gradle wrapper assembleDebug '
      }
    }
  }
}
