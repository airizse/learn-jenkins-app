pipeline {
    agent any

    stages {
        stage('w/o Docker') {
            steps {
                sh '''
                    echo "Without Docker"
                    ls -lart
                '''
            }
        }
        stage('w/ Docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "With Docker"
                    npm --version
                    ls -lart
                    touch containerPokedYou.txt
                '''
            }
        }
    }
}
