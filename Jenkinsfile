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
                cleanWs()
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                    
                '''
            }
        }
    }
}
