pipeline {
    agent any

    tools {
        maven 'Maven-3.9.16'
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Code downloaded from GitHub'
            }
        }

        stage('Maven Goals') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('HTML') {
            steps {
                echo 'HTML processing will happen here'
            }
        }
    }
}
