pipeline {
    agent any

    tools {
        maven 'maven-3.9' // Assure-toi que ce nom correspond à celui configuré dans Jenkins (configuration Maven)
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ibou0188/simple-springboot-app.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
    
    post {
        success {
            echo 'Build réussi !'
        }
        failure {
            echo 'Build échoué !'
        }
    }
}
