pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo '---------- Building... ----------'
                sh 'npm install'
                sh 'npm run build'
                echo '---------- Build complete! ----------'
            }
        }

        stage('Lint') {
            steps {
                echo '---------- Linting... ----------'
                sh 'npm install'
                sh 'npm run lint'
                echo '---------- Lint complete! ----------'
            }
        }
        
        stage('Test') {
            steps {
                echo '---------- Testing... ----------'
                sh 'npm install'
                sh 'npm test'
                echo '---------- Test complete! ----------'
            }
        }
        
        stage('Deploy') {
            steps {
                echo '---------- Deploying... ----------'
                echo '---------- Deploy complete! ----------'
            }
        }
    }

    post {
        // If the pipeline fails, send an email notification
        failure {
            echo '!!!!!!!!!! Pipeline failed! !!!!!!!!!!'
            mail to: 'ynwdldn03+dev@gmail.com',
                subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                body: "Something is wrong with ${env.BUILD_URL}"
        }
        // If the pipeline is successful, print a message
        success {
            echo '########## Pipeline successful! ##########'
        }
    }
}