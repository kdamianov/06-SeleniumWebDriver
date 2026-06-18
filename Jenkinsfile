pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Setup .NET') {
            steps {
                bat 'dotnet --version'
            }
        }

        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run TestProject1 tests') {
            steps {
                bat 'dotnet test TestProject1/TestProject1.csproj --no-build --verbosity normal'
            }
        }

        stage('Run TestProject2 tests') {
            steps {
                bat 'dotnet test TestProject2/TestProject2.csproj --no-build --verbosity normal'
            }
        }

        stage('Run TestProject3 tests') {
            steps {
                bat 'dotnet test TestProject3/TestProject3.csproj --no-build --verbosity normal'
            }
        }
    }
}
