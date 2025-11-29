pipeline {
    agent any
    // Define Parameters
    parameters {
        string(name: 'VERSION', defaultValue: '', description: 'version to deploy')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
    }
    environment {
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building version ${NEW_VERSION}"
                // Windows users use 'bat', Mac/Linux use 'sh'
                bat 'echo "Simulating NVM install or Tool usage"' 
            }
        }
        stage('Test') {
            // Only run if the checkbox is checked
            when {
                expression { return params.executeTests }
            }
            steps {
                echo 'Testing Project'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying version ${params.VERSION}"
            }
        }
    }
}
