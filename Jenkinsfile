 pipeline {
    agent any

    environment {
        DOTNET_SDK = 'dotnet'  // make sure 'dotnet' is in PATH
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/axelma199/myapp.git'
            }
        }

        stage('Restore') {
            steps {
                bat "${DOTNET_SDK} restore"
            }
        }

        stage('Build') {
            steps {
                bat "${DOTNET_SDK} build --configuration Debug"
            }
        }

        stage('Run') {
            steps {
                bat "${DOTNET_SDK} run --project MyApp.csproj"
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
