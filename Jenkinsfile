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
                sh 'sudo cp /var/lib/jenkins/workspace/Pipeline2/target/demo.war /home/ubuntu/apache-tomcat-9.0.97/webapps' 
                sh 'sudo bash /home/ubuntu/apache-tomcat-9.0.97/bin/shutdown.sh'
                sh 'sudo bash /home/ubuntu/apache-tomcat-9.0.97/bin/startup.sh'  //comment
            }
        }
    }
}
