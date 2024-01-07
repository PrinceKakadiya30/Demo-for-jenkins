pipeline {
    agent {label 'agent-1'}

    stages {
        stage('Git Clone') {
            steps {
                git branch: 'develop', changelog: false, poll: false, url: 'https://github.com/PrinceKakadiya30/Demo-for-jenkins.git'
            }
        }

        stage('Pre Build') {
            steps {
                script {
                    sh '''
                        npm install
                    '''
                }
            }
        }

        stage('Test') {
            steps {
                sh '''
                    npm test
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                    npm run build
                '''
            }
        }
    }
}
