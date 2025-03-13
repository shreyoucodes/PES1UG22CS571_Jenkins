pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
        build 'PES1UG22CS571'
        sh 'g++ main.cpp -o output'
      }
    }
    stage('Test'){
      steps{
        sh './output'
      }
    }
    stage('Deploy'){
      steps{
        echo 'deploy'
      }
    }
  }
  post{
      failure{
        echo 'Pipeline Failed'
      }
    }
}
