
pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Backend') {
            steps {
                dir('backend') {
                    bat 'mvnw.cmd -B -DskipTests clean package'
                }
            }
        }
    }

    post {
        success {
            echo 'Smart Incident Management backend build succeeded.'
        }
        failure {
            echo 'Build failed. Check the Jenkins Console Output.'
        }
    }
}
