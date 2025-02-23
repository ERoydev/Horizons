pipeline {
    agent any

    environment {
        DOTNET_ROOT = '/root/.dotnet'
        PATH = "${DOTNET_ROOT}:${env.PATH}"
    }

    stages {
        stage('Verify .NET Version') {
            steps {
                sh 'echo $PATH'
                sh 'which dotnet'
                sh 'dotnet --info'
            }
        }

        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }

           stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }

           stage('Test') {
            steps {
                sh 'dotnet test --no-build --verbosity-normal'
            }
        }
    }
}