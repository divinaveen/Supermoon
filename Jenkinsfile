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
    stage('PUsh Docker Image')
       {
       steps{
         withCredentials([string(credentialsId: 'hubpass', variable: 'Hpas')]) {
         sh "docker login -u naveendivi -p ${Hpas}"
         sh "docker push naveendivi/japp:${TAG}"
}
}


      }
}
}

def gittag() {
      def tag = sh script: 'git rev-parse HEAD', returnStdout: true
      return tag
}
