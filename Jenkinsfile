pipeline {
    agent { 
        docker {
            image 'alpine/git' // or your image
            args '-v /home/klx/jenkins-101:/repo'
        }
    }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                echo "Try to trigger Jenkins build from local repo"
                sh '''
                cd src
                cat index.js
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}