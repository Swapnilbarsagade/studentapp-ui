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

        stage ('build') {
            steps {
                sh '/opt/apache-maven/bin/mvn clean package'
            }
        }
    }
}