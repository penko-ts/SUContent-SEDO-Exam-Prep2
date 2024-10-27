pipeline {
    agent any

    stages {
        stage('Restore Dependencies') { 
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet restore' 
            }
        }
        stage('Dotnet Build') { 
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Execute Tests') { 
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal' 
            }
        }
    }
}
