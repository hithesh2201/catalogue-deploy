pipeline {
    agent {
        label 'agent-1'
    }
    // agent any
    environment {
        packageversion= "$parmas.packageversion"
    }
    parameters {
        choice(name: 'CHOICE', choices: ['Dev', 'QA', 'Prod'], description: 'Pick something')
    }

    options {
        timeout(time: 1, unit: 'HOURS') // Set a timeout for the entire pipeline
        ansiColor("xterm") 
        disableConcurrentBuilds()
    }

    stages {
        stage('Get version from Json previous job') {
            steps {
                script {
                    echo "version : $packageversion"
                }
            }
        }

        stage('install dependencies') {
            steps {
                sh"""
                    
                """
            }
        }

        stage('Sonar Scan'){
            steps{
                sh """
                    
                """
            }
        }

        stage('Build artifact') {
            steps {
                sh """
                    
                """
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully. Sending notification..."
            // Add notification steps for successful builds
        }

        failure {
            echo "Pipeline failed. Sending notification..."
            // Add notification steps for failed builds
        }

        always {
            echo "Cleaning up..."
            // Add any cleanup steps that should run regardless of success or failure
        }
    }
}
