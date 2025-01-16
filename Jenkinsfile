pipeline {
    agent any
    environment {
       Sample_creds = credentials('JFROG')
    }
       stages 
    {
        stage('checkout') {             
            steps {
                sh """
                #!/bin/bash
                sleep 5
                sudo su
                cd /opt/apache-tomcat-10.1.34/webapps
                curl -L -u "JFROG_USR:JFROG_PSW" "http://3.110.127.190:8082/artifactory/hello-world-war-libs-release/com/efsavage/hello-world-war/1.0.39/hello-world-war-1.0.39.war"
                pwd
                cd /opt/apache-tomcat-10.1.34/bin
                ./shutdown.sh
                sleep 3
                pwd
                cd /opt/apache-tomcat-10.1.34/bin
                ./startup.sh
                sleep 3
                """ 

            }
        }
         
    }
}
