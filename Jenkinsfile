pipeline {
    agent any

    environment {
        PATH = "/root/.dotnet:$PATH"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Verify .NET Installation') {
            steps {
                sh 'dotnet --info'
            }
        }

        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }

        stage('Run UI Test for Project1') {
            steps {
                sh 'dotnet test TestProject1/TestProject1.csproj --no-build --verbosity normal'
            }
        }

        stage('Run UI Test for Project2') {
            steps {
                sh 'dotnet test TestProject2/TestProject2.csproj --no-build --verbosity normal'
            }
        }

        stage('Run UI Test for Project3') {
            steps {
                sh 'dotnet test TestProject3/TestProject3.csproj --no-build --verbosity normal'
            }
        }
    }
}
