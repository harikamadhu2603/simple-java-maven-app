pipeline {
  agent any
  stages {
      stage("scm checkout"){
          steps{
              git 'https://github.com/jenkins-docs/simple-java-maven-app.git'
          }
      }
    stage("Build") {
      steps {
        sh 'mvn clean package'
      }
    }
    
  }
  post {
    always {
        echo "hey"
    }
    success {
      mail to:"harikamadhu123@gmail.com", subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed."
    }
    failure {
      mail to:"harikamadhu123@gmail.com", subject:"FAILURE: ${currentBuild.fullDisplayName}", body: "Boo, we failed."
       }
  }
}
