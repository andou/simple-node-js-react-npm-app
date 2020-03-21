pipeline {
    agent {
        docker {
            image 'node:8-alpine' 
            args '-v /var/builds:/home -p 3000:3000 --dns 10.41.255.5'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'touch pippo.txt'
            }
        }
    }
}
