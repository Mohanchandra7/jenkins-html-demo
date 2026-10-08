pipeline {
    agent any

    parameters {
        string(
            name: 'NAME',
            defaultValue: 'Surendra Reddy',
            description: 'Enter the name'
        )
    }

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
                echo "Creating HTML for ${params.NAME}"

                bat """
                (
                    echo ^<!DOCTYPE html^>
                    echo ^<html^>
                    echo ^<head^>
                    echo ^<title^>Jenkins HTML Page^</title^>
                    echo ^</head^>
                    echo ^<body^>
                    echo ^<h1^>Hello ${params.NAME}^!^</h1^>
                    echo ^<p^>This HTML file was created by Jenkins.^</p^>
                    echo ^</body^>
                    echo ^</html^>
                ) > output.html
                """
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'output.html', fingerprint: true
        }
    }
}
