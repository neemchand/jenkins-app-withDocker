pipeline {
        agent {
         node {
            label '' 
        }
    }

    
    environment {
        APP_VERSION = '1'
    }
    stages {
        stage('Build') {
            steps {
                   sh 'php --version'
            }
        }
        stage('Test') {
            steps {
                echo 'run unit test'
            }
        }
        stage('Deploy to UAT') {
            steps {
                echo 'Deploying to uat..3' 
                sh 'git show-ref'
                sh 'git push https://heroku:b90f6c35-7b07-4c13-a262-26cee3b241e0@git.heroku.com/neem-jenkins-app.git HEAD:heroku master'
               
            }
        }
    }
    post {
        always {
          echo 'test Done...1.'
      }

      success {
          echo 'test ...2.'
      }

      failure {
          echo 'failure'
      }
    }
}