pipeline
{
    agent any
    stages
    {
        stage("checkout")
        {
            steps
            {
                git 'https://github.com/vaddeadiseshu/game-of-life.git'
            }
           
        }
        stage("build")
        {
            steps
            {
               sh label: '', script: 'mvn package'
                
            }
        
        }
        stage("sonarqube analysis")
        {
            environment 
            {
            scannerHome = tool 'SonarQubeScanner'
            }
            steps
            {
                withSonarQubeEnv('sonarqube')
                {
                     sh "${scannerHome}/bin/sonar-scanner"
                }
                timeout(time: 10, unit: 'MINUTES')
                 {
                waitForQualityGate abortPipeline: true
                 }
            }
        }
    }
    
}