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
    }
    
}