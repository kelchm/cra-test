pipeline {
    agent {
      docker { image 'node:10-alpine' }
    }
    environment {
        HOME = '.'
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm i -ci'
                sh 'npm run build'
                sh 'npm install @modus/gimbal'
            }
        }

        // stage('Build') {
        //     steps {
        //         sh 'npm run build'
        //     }
        // }

        stage('Run Gimbal') {
            steps {
                sh 'ls -lah'
                sh 'gimbal audit'
            }
        }
    }
}
