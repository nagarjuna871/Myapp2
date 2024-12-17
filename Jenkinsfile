pipeline {
    agent {
        label 'jenkins-master'
    }
    
    environment {
        Version = '1.0.0' // Set a default version
    }
    
    stages {
        stage('Compile') {
            steps {
                powershell 'mvn compile -DVer=$env:Version'
            }
        }
        
        stage('Junit') {
            steps {
                bat 'mvn test -DVer=%Version%'
            }
        }
        
        stage('Package') {
            steps {
                bat 'mvn -DskipTests clean package -DVer=%Version%'
            }
        }

        stage('Upload package into Nexus') {
            steps {
                bat 'mvn -DskipTests deploy -DVer=%Version%'
            }
        }        
        
        stage('Cleanup Workspace') {
            steps {
                cleanWs()
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs for details.'
        }
    }
}
