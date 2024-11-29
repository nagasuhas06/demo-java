pipeline {
    agent any
    stages {
        stage('Git clone') { 
            steps {
                git 'https://github.com/Shreenivas123/demo-java.git'
            }
        }
        stage('Build') { 
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy to tomcat') { 
            steps {
                sh 'echo "i am Deploying"'
                sh 'sudo cp /var/lib/jenkins/workspace/target/demo.war /home/ubuntu/tomcat/apache-tomcat-10.1.12/webapps/' 
                sh 'sudo bash /home/ubuntu/apache-tomcat-9.0.97/bin/.shutdown.sh'
                sh 'sudo bash /home/ubuntu/apache-tomcat-9.0.97/bin/.startup.sh'  //comment
            }
        }
    }
}
