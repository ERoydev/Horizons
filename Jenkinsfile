pipeline {
    agent {
        docker {
            image 'mcr.microsoft.com/dotnet/sdk:8.0'
        }
    }

    stages {


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