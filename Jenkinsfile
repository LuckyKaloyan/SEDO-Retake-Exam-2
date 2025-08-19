pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm 
            }
        }
        stage('Restore the project') {
            when { branch 'main' }
            steps {
                bat 'dotnet restore Homies.sln'
            }
        }

        stage('Build the project up') {
            when { branch 'main' }
            steps {
                bat 'dotnet build Homies.sln'
            }
        }

        stage('Test the project') {
            when { branch 'main' }
            steps {
                bat 'dotnet test Homies.sln --no-build --verbosity normal'
            }
        }
    }
}
