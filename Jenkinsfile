pipeline {
    agent any
    parameters {
        string(name: 'NAME', description: 'Please tell me your name?')
 
        text(name: 'DESC', description: 'Describe about the job details')
 
        booleanParam(name: 'SKIP_TEST', description: 'Want to skip running Test cases?')
 
        choice(name: 'BRANCH', choices: ['Master', 'Dev'], description: 'Choose branch')
 
        password(name: 'SONAR_SERVER_PWD', description: 'Enter SONAR password')
    }       
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
        
        stage('Printing Parameters') {
            steps {
                echo "Hello ${params.NAME}"

                echo "Job Details: ${params.DESC}"

                echo "Skip Running Test case ?: ${params.SKIP_TEST}"

                echo "Branch Choice: ${params.BRANCH}"

                echo "SONAR Password: ${params.SONAR_SERVER_PWD}"
            }
        }
        stage('Postdeploy') {
          steps {
            echo 'Postdeployment phase....'
          }
        }
    }
}
