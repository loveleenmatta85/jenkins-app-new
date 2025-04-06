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
                    npm ci
                    npm run build
                                       
                '''
            }
        }
        stage('Testing the Npm application') {
            agent {

                docker {
                    image 'node:current-bullseye-slim'
                    reuseNode true
                }
            }
            steps {
                
                sh '''
                    test -e build/index.html
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    npm test
                    echo "Testing the NPM application is successful"

                                       
                '''
            }
        }
    }
}
