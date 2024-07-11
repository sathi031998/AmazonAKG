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
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Deploy') {
            steps {
                script {
                    def tomcatURL = 'http://localhost:8087/manager/text'
                    def warFile = 'target/Amazon.war'
                    def contextPath = 'Amazon'
                    def tomcatUser = 'your-tomcat-username'
                    def tomcatPassword = 'your-tomcat-password'
                    
                    sh """
                        curl --upload-file ${warFile} \
                            --user ${tomcatUser}:${tomcatPassword} \
                            ${tomcatURL}/deploy?path=/${contextPath}&update=true
                    """
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

       
