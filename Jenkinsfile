pipeline {
    agent {
  label 'jenkins-master'
         }

    stages {
        stage('Compile') {
            steps {
		powershell 'mvn compile -DVer=$Version'
            }
        }
        
        
        stage('Junit') {
            steps {
		bat 'mvn test -DVer=$Version'
                  }
        }
        stage('Package') {
            steps {
		bat 'mvn -DskipTests clean package -DVer=$Version'
                  }
        }

        stage('Upload package into Nexus') {
            steps {
		bat 'mvn -DskipTests deploy -DVer=$Version'
                  }
        }        
        stage('Cleanup Workspace') {
            steps {
                cleanWs()
            }
        }
    }
}
