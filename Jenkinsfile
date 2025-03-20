pipeline {
  agent any
  stages {
    stage('BuildStage') {
      steps {
        git(url: 'https://github.com/Narumalar/jenkins-training', branch: 'master', credentialsId: 'github_user')
        sh '''docker build -t narumalar/repo1:latest .








'''
        sh 'docker push narumalar/repo1:latest'
      }
    }

    stage('DeployDev') {
      parallel {
        stage('DeployDev') {
          steps {
            sh 'echo "Deploy"'
          }
        }

        stage('DeployQA') {
          steps {
            echo 'qa stage'
          }
        }

      }
    }

  }
}