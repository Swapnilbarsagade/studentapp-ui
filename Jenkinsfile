pipeline {
    agent {
        label 'master'
    }
    
    stages {
        stage('pull') {
            steps {
                echo 'Pulling the source code'
                git 'https://github.com/Swapnilbarsagade/studentapp-ui.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application.'
                sh '/opt/apache-maven/bin/mvn clean package'
            }
        }
        stage('Test') {  // Define a stage named "Test"
            steps {
                echo 'Running tests...'  // Command or script to run
            }
        }
        stage('Deploy') {  // Define a stage named "Deploy"
            steps {
                echo 'Deploying the application...'  // Command or script to run
            }
        }
    }
}
