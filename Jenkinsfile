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
        sh ' chmod -R 777 .'
        sh ' export ANDROID_HOME=/home/ubuntu/Android/Sdk'
        sh ' export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools'
        sh 'source ~/.bashrc ' 
        sh './gradlew wrapper'
        sh './gradlew clean '
        sh './gradlew  assembleDebug '
      }
    }
  }
}
