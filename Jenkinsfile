pipeline {
    agent any

    tools {
        maven 'Maven_Home'  // Name of Maven installation in Jenkins
    }

    options {
        skipDefaultCheckout(true)
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'branch', 
                    url: 'https://github.com/developerD4/Jenkins.git', 
                    credentialsId: 'Git-logIn-access'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'mvn test'

                // Publish test results to Jenkins
                //junit '**/target/surefire-reports/*.xml'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging the application...'
                // Uncomment below if you want Maven package explicitly
                // bat 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deployment commands here
                // Example: bat 'copy target\\*.jar D:\\Deployments\\'
            }
        }
    }

    post {
        failure {
            echo 'Build Failed!'
        }
        success {
            echo 'Build Succeeded!'
        }
    }
}

