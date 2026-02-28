pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/samidhaskale/nodeapp.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                dir('nodeapp') {
                    sh 'npm install'
                }
            }
        }

        stage('Run App') {
            steps {
                dir('nodeapp') {
                    sh '''
                    node index.js &
                    sleep 5
                    pkill node || true
                    '''
                }
            }
        }

    }
}
