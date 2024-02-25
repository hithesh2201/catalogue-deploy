pipeline {
    agent {
        label 'agent-1'
    }
    // agent any
    environment {
        packageversion= "$packageversion"
    }
    parameters {
        choice(name: 'environment', choices: ['dev', 'prod'], description: 'Pick something')
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

        stage('Init') {
            steps {
                sh"""
                     cd terraform
                     terraform init --backend-config=${params.environment}/backend.tf -reconfigure

                """
            }
        }

        stage('plan'){
            steps{
                sh """
                    cd terraform
                    terraform plan -var="app_version=$packageversion"
                """
            }
        }

        stage('apply') {
            steps {
                sh """
                    cd terraform
                    
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
