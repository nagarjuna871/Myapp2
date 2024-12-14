pipeline {
    agent {
  label 'jenkins-master'
}


    stages {
        stage('checkout code from SCM') {
            steps {
               git branch: 'main', url: 'git@github.com:nagarjuna871/Myapp2.git'
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
