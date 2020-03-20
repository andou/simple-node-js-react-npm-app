pipeline {
    agent {
        docker {
            image 'node:8-alpine' 
            args '-v /var/www/html/pippo:/home/ -p 3000:3000 --dns 10.41.255.5'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                sh './jenkins/scripts/kill.sh' 
            }
        }
    }
}
