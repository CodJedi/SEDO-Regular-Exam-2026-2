pipeline {
    agent any

    stages {
        stage('Build and Test on main') {
            when {
                branch 'main'
            }
            steps {
                sh 'dotnet --info'
                sh 'dotnet restore'
                sh 'dotnet build --configuration Release --no-restore'
                sh 'dotnet test --configuration Release --no-build'
            }
        }

        stage('Skip non-main') {
            when {
                not { branch 'main' }
            }
            steps {
                echo 'Skipping build/test because this is not main branch.'
            }
        }
    }
}