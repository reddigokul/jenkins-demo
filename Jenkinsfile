pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building.. This is the build phase'
            }
        }
        stage('Test') {
            steps {
                step{
                    echo 'Testing.. This is the testing phase'
                }
                step{
                    input('Can We approve?......')
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....  This is the deployment phase'
            }
        }
        stage('Postdeploy') {
          steps {
            echo 'Postdeployment phase....'
          }
        }
    }
}
