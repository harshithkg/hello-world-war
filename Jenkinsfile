pipeline {
    agent { label 'slave-1' }
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/shrikantashetty/hello-world-war.git'
            }
        } 
       stage('build') {
            steps {
                sh 'cd hello-world-war'
                sh 'mvn clean package'
            }
        }
      
}
}
