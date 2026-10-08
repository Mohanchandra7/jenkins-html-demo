pipeline {
    agent any

    tools {
        jdk 'JDK-21'
        maven 'Maven-3.9.16'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Mohanchandra7/jenkins-html-demo.git'

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
