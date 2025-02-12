pipeline {
    agent {
        label "dummy"
    }

    stages {
        stage ('Pull') {
            steps {
                git 'https://github.com/Swapnilbarsagade/studentapp-ui.git'
            }
        }

        stage ('Build') {
            steps {
                sh '/opt/apache-maven/bin/mvn clean package'
            }
        }

        stage ('Test') {
            steps {
                echo 'Testing the source code'
            }
        }

        stage ('Deploy') {
            steps {

            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}