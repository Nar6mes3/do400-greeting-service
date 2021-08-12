pipeline{
    agent{
        label "nodejs"
    }
    stages{
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage("Check Style"){
            steps{
                echo "checkstyles is not working"
                //sh "npm run lint"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }

        stage('Deploy') {
          steps {
              sh '''
                  oc project muwtnp-greetings
                  oc start-build greeting-service --follow --wait
              '''
          }
      }
    }
}
