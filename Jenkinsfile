pipeline {
    agent {
        docker {
            image 'node:8-alpine' 
            args '-v /var/builds:/var/builds -p 3000:3000 --dns 10.41.255.5'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'touch /var/www/node-builds/pippo.txt'
            }
        }
        stage('Deliver') {
            steps {
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
            }
        }
    }
}
