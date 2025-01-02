pipeline {
    agent { label 'slave-1' }
    stages {
        stage('checkout') {
            steps {
               // sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/shrikantashetty/hello-world-war.git'
            }
        } 
       stage('build') {
            steps {
                sh 'cd hello-world-war'
                sh 'mvn clean package'
            }
        }
        stage('deploy') {
           steps {
             sh 'cp /home/slave-1/jenkins/workspace/pipeline/target/hello-world-war-1.0.0.war /var/lib/tomcat10/webapps/'
               }
          }
    }
post {
    success {
        mail to: "harshithkgph27@gmail.com",
             subject: "Jenkins Job Success",
             body: "The Jenkins job completed successfully."
    }
    failure {
        mail to: "harshithkgph27@gmail.com",
             subject: "Jenkins Job Failed",
             body: "The Jenkins job failed. Check the logs for details."
    }
      
}
}
