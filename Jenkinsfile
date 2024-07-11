pipeline {
    agent any
    stages {
        stage('Pull') {
            steps {
                git url: 'https://github.com/sathi031998/AmazonAKG.git'
            }
        }
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Build') 
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    def tomcatURL = 'http://your-tomcat-server:8080/manager/text'
                    def warFile = 'target/Amazon.war'
                    def contextPath = 'Amazon'
                    def tomcatUser = 'your-tomcat-Sathi'
                    def tomcatPassword = 'your-tomcat-sathi123'
                    
                    sh 
                        curl --upload-file ${Amazon.war} \
                            --user ${Sathi}:${sathi123} \
                            ${localhost:8087}/deploy?path=/${Amazon.war}&update=true
                
                }
            }
        }
    }
    post {
        failure {
            echo 'Failure in the build'
        }
        success {
            echo 'Build and Deployment Successful'
        }
    }
}


