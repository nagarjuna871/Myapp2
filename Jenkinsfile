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
            stage('compile') {
                steps {
              powershell 'mvn compile'
            }
        }
         stage('test') {
            steps {
             powershell 'mvn test'
            }
        }
         stage('deploy') {
            steps {
                echo 'deploy steps'
            }
        }
    }
}
