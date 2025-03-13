pipeline{
  agent any
  stages{
    stage('Build'){
      steps{
        sh 'mvn clean install'
        echo 'Build Stage Successful'
        sh 'g++ jenkinstest.cpp -o PES1UG22CS571-1'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
        echo 'Test Stage Successful'
        post {
          always{
            junit 'target/surefire-reports/*.xml'
          }
        }
        sh './PES1UG22CS571-1'
      }
    }
    stage('Deploy'){
      steps{
        sh 'mvn deploy'
        echo 'Deployment Successful'
        sh 'echo "Deployment successful!"'
      }
    }
    post{
      failure{
        echo 'Pipeline Failed'
      }
    }
  }
}
