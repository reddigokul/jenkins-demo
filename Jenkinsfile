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
                parallel(
                    "step-1": {
                        echo 'Testing.. This is the testing phase Step One'
                    },
                    "step-2":  {
                        input('Can We approve?......')
                        echo 'Testing.. This is the testing phase Step Two'
                    }
                )
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
