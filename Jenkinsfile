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
              post {
                
                success {
                    emailext  subject: 'Unit Test Status - Success', 
                              body: 'Unit Test has been completed successfully.', 
                              to: "bhullarekam04@gmail.com",
                              attachLog: true
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
             post {
                
                success {
                    emailext  subject: 'Deploy', 
                              body: 'Deploy has been completed successfully.', 
                              to: "bhullarekam04@gmail.com",
                              attachLog: true
                }
        }
        stage('Approval') {
            steps {
                sleep time: 10, unit: 'SECONDS'
            }
        }
         stage('Approval updated') {
            steps {
                sleep time: 10, unit: 'SECONDS'
            }
        }
      
    }
}
