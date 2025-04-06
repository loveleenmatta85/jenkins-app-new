pipeline {
    agent any
    environment {
    NPM_CONFIG_CACHE = "${WORKSPACE}/.npm"
}
    stages {
        
        stage('Build NPM App') {
            agent {

                docker {
                    image 'node:current-bullseye-slim'
                    reuseNode true
                }
            }
            steps {
                
                sh '''
                    ls -ltra
                    node --version
                    npm --version
                    npm install
                                       
                '''
            }
        }
    }
}
