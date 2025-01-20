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
                sh '''mvn sonar:sonar \\
                      -Dsonar.projectKey=studentapp \\
                      -Dsonar.host.url=http://43.202.4.118:9000 \\
                      -Dsonar.login=c652d62e07606f1f9c0f22cc9e37a30e72bc372e'''
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
