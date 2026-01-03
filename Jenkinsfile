pipeline {
    agent { 
        node {
            label 'docker-agent-alpine'
        }
    }
    options {
        timestamps()
        disableConcurrentBuilds()
    }
    triggers {
        pollSCM 'H * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                echo "Try to change triggers to explore if Jenkins read it"
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