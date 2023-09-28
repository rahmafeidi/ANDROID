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
        sh ' chmod -R 777 *
        sh ' export ANDROID_SDK_ROOT=/home/ubuntu/Android/Sdk'
        sh './gradle wrapper'
        sh './gradlew clean '
        sh './gradlew  assembleDebug '
      }
    }
  }
}
