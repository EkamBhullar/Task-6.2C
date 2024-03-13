pipeline {
    agent any
    environment {
        DIRECTORY_PATH = "https://github.com/EkamBhullar/NewRepo"
        TESTING_ENVIRONMENT = "junit"
        PRODUCTION_ENVIRONMENT = "Ekamjot"
    }

    stages {

        stage('Build') {
            steps {
                echo "Fetching the source code from the directory path specified by ${env.DIRECTORY_PATH}"
                echo "compile the code and generate any necessary artifacts"
            }
        }
        stage('Test') {
            steps {
                echo "unit tests"
                echo "integration tests"
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "check the quality of the code"
            }
        }
        stage('Deploy') {
            steps {
                echo "deploy the application to a testing environment specified by the ${env.TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval') {
            steps {
                sleep time: 10, unit: 'SECONDS'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Code Deployed succesfully to ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
