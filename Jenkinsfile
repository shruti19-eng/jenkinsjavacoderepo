pipeline {
    agent {label 'Slave1'}
    
    tools {
        maven 'Maven 3.6.3'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',url:'https://github.com/AmitPrajapati9401/jenkinsjavacoderepo.git'  // Replace with actual repo
            }
        }

        stage('Build') {
            steps {
                dir('Javarepo1') {  // Change to actual repo folder
                    bat 'mvn clean package'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed!'
        }
    }
}
