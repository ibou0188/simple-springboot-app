pipeline {
    agent any

    tools {
        maven 'Maven' // Le nom que tu as défini dans Jenkins (Global Tool Configuration)
        jdk 'JDK'     // Idem pour le JDK
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/ibou0188/simple-springboot-app.git'
            }
        }

        stage('Build') {
            steps {
                dir('simple-springboot-app') {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Test') {
            steps {
                dir('simple-springboot-app') {
                    sh 'mvn test'
                }
            }
        }
    }

    post {
        failure {
            echo 'Build échoué !'
        }
    }
}
