pipeline {
    agent any

    environment {
        VERSION = "1.0"
    }

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run test stage')
    }

    tools {
        maven 'Maven'   // Make sure name matches Jenkins tools config
    }

    stages {
        stage('Build') {
            steps {
                echo "Building version ${VERSION}"
            }
        }

        stage('Test') {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo "Testing..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying..."
            }
        }
    }

    post {
        always {
            echo "Pipeline Finished"
        }
    }
}
