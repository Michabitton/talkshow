node {
   stage('Checkout') {
     checkout scm
   }
   stage('Build') {
       dir("advance/workshop/talkshow"){
          sh 'python3 -V'
          sh 'python3 -m venv venv'
          sh 'source venv/bin/activate'
          sh ''
        // build
       }
     }
   stage('test') {
       dir("advance/workshop/talkshow"){
        // test
       }
     }
   stage('Serve') {
    dir("advance/workshop/talkshow"){
        // serve
       }
    }
   stage('docker build/push') {
    //  docker build and push
   }
   stage('docker run') {
    //  docker run
   }
}