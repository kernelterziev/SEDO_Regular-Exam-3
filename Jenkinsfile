pipeline {
    agent any
    
    triggers {
        pollSCM('H/5 * * * *')
    }
    
    stages {
        stage('Build') {
            steps {
                bat 'dotnet build Horizons.sln'
            }
        }
        stage('Unit Tests') {
            steps {
                bat 'dotnet test Horizons.Tests.Unit/Horizons.Tests.Unit.csproj'
            }
        }
        stage('Integration Tests') {
            steps {
                bat 'dotnet test Horizons.Tests.Integration/Horizons.Tests.Integration.csproj'
            }
        }
    }
}