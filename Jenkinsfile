pipeline {
    agent any

    stages {
        
        stage('Build NPM App') {
            agent {

                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                
                sh '''
                    ls -ltra
                    node --version
                    npm --version
                     exec su-exec npm ci 
                                       
                '''
            }
        }
    }
}
