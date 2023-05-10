pipeline {
    agent any
    tools {nodejs "node"}
    environment {
        HOME = '.'
    }
    triggers {
        pollSCM "* * * * *"
    }
    stages {
        stage('Build Application') { 
            steps {
                echo '=== Building Notes Application ==='
                sh 'npm install' 
                // sh 'cd frontend' 
                //echo ' ==> Present working directory <== '
                //sh 'npm install'
            }
        }
        stage('Test Application') {
            steps {
                echo '=== Testing Notes Application ==='
                // sh 'npm test'
            }
        }
        stage('Deliver') { 
            steps {
                //sh "chmod +x -R ${env.WORKSPACE}"
                //sh './jenkins/scripts/deliver.sh'
                sh 'npx sst deploy --stage prod -y'
            }
        }
    }
}
