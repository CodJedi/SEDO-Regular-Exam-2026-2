pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            when {
                branch 'main'
            }
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build the app') {
            when {
                branch 'main'
            }
            steps {
                sh 'dotnet build --no-restore --configuration Release'
            }
        }

        stage('Run the tests') {
            when {
                branch 'main'
            }
            steps {
                sh 'dotnet test --no-build --configuration Release --verbosity normal'
            }
        }
    }
}