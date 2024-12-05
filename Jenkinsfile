pipeline {
    agent {
  label 'jenkins-master'
}


    stages {
        stage('checkout code from SCM') {
            steps {
                git branch: 'feature1', url: 'https://github.com/bhanu833/my-app2.git'
            }
        }
         stage('test') {
            steps {
                echo 'test steps'
            }
        }
         stage('deploy') {
            steps {
                echo 'deploy steps'
            }
        }
    }
}
