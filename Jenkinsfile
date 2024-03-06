pipeline {
  agent any
  stages {
    stage ('Clone repository') {
      steps {
        checkout ([$class: 'GitSCM', 
                   branches: [[name: '*/main']],
                   userRemoteconfigs: [[url: 'https://github.com/Riya302/RiyaBansal_929_Jenkins.git']]])
      }
    }
    stage ('Build') {
      steps {
        build 'PES1UG21CS929-1'
        sh 'g++ new.cpp -o output'
      }
    }
    stage ('Test') {
      steps {
        sh './output'
      }
    }
    stage('Deploy'){
      steps {
        echo 'deploy'
      }
    }
  }
  post{
    failure{
      error 'Pipeline failed'
    }
  }
}
