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
                echo 'building the source code'
            }
        }
    }
}