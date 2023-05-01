node {
   stage('Checkout') {
     checkout scm
   }
   stage('Build') {
        sh 'apt-get update -y'
        sh 'python3 -V'
        sh 'apt install python3.10-venv -y'
        sh label: '',
        script: '''
        pip install -e '.[dev]'
        pip install email_validator
        '''
        // build
     }
   stage('test') {
        sh 'py.test  -v --cov-config .coveragerc --cov=talkshow -l --tb=short --maxfail=1 tests/'
     }
   stage('Serve') {
        sh 'flask adduser -u admin -p 1234'
        sh '''
        flask addevent -n "Flask Conf" -d "2018-08-25"
        '''
        sh 'flask run'
    }
   stage('docker build/push') {
        sh 'docker build . -t flaskapp --build-arg USERNAME=micha'
    //  docker build and push
   }
   stage('docker run') {
    //  docker run
   }
}