pipeline {
    agent any

    stages {
        stage('Pulling code from SCM') {
            steps {
                echo 'Pulling...'
            }
        }
      stage('Deploy') {
            steps {
                  input message: 'Do you want to deploy website? (click "Proceed" to continue)'
                  sh 'aws s3 cp . s3://devopsdemo2022   --recursive'
            }
        }   
        stage('Setting Permissions') {
            steps {
                  sh 'aws s3 website  s3://devopsdemo2022/   --index-document index.html  --error-document error.html'
            }
        }
    }
}
