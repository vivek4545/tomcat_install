pipeline {
  agent {
    node {
      label 'VK-4'
    }

  }
  stages {
    stage('Checkout') {
      parallel {
        stage('Checkout') {
          steps {
            git(url: 'https://github.com/vivek4545/tomcat_install.git', branch: 'dev', credentialsId: 'Githubentry', poll: true)
          }
        }

        stage('build') {
          steps {
            ansiblePlaybook 'tomcat_install.yaml'
          }
        }

      }
    }

    stage('test') {
      steps {
        echo 'test done'
      }
    }

    stage('quality code analysis') {
      steps {
        sh 'echo " hello all"'
      }
    }

  }
}