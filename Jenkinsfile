pipeline {
    agent any
    stages {
stage('pull') {
            steps {
                git url: 'https://github.com/sathi031998/AmazonAKG.git'
            }
        }
        
        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }

    }

  post{
    
  failure{
       echo 'Failure in the build'
   }

  }


}
