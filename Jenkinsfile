pipeline {
    agent {
  label 'jenkins-master'
}
    stages {
            stage('compile') {
                steps {
                    powershell 'mvn compile'
                  }
              }
        
            stage('junit') {
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
