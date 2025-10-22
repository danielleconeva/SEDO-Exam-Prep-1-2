pipeline{
    agent any
    
    stages{
        stage("Restore the dependencies"){
            when { 
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps{
                sh 'dotnet restore' 
            }
        }
        stage("Build the application"){
            when { 
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps{
                sh 'dotnet build --no-restore' 
            }
        }
        stage("Run the tests"){
            when { 
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps{
                sh 'dotnet test --no-build --verbosity normal' 
            }
        }
    }
}