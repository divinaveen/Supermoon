pipeline{
    agent any
    
stages{
   stage('Build Docker Image')
        {
      steps{
          sh "docker build -t  naveendivi/japp:v1 ."
        }


       }

      }
}


def gittag() {
      def tag = sh script: 'git rev-parse HEAD', returnStdOut: true
      return tag
}
