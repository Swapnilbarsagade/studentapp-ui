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
        stage('Test') {
            steps {
                echo 'Running tests...'
                withSonarQubeEnv(installationName: 'sonar', credentialsId: 'sonartoken') {
                    sh '/opt/apache-maven/bin/mvn sonar:sonar -Dsonar.projectKey=studentapp'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh '''/opt/apache-tomcat/bin/catalina.sh stop
                      mv target/*.war /opt/apache-tomcat/webapps/student.war
                      /opt/apache-tomcat/bin/catalina.sh start'''
            }
        }
    }
}
