pipeline{
    agent any
    environment {
        TAG = gittag()
             }    
stages{
   stage('Build Docker Image')
        {
      steps{
          sh "docker build . -t  naveendivi/japp:${TAG}"
        }

       }

      }
}


def gittag() {
      def tag = sh script: 'git rev-parse HEAD', returnStdout: true
      return tag
}
