pipeline {
    agent any
    // Define Global Variable
    environment {
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building Project'
                echo "Building version ${NEW_VERSION}" // Using the variable
            }
        }
        stage('Test') {
            // Add Conditional
            when {
                expression { return env.NEW_VERSION == '1.3.0' } // Example condition
            }
            steps {
                echo 'Testing Project'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post { always { echo 'Done' } }
}
