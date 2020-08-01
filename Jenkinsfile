// jenkins file using the scripted pipeline

node{
    stage('SCM') {
        git 'https://github.com/vaddeadiseshu/game-of-life.git'
    }
    stage('Build'){
        sh label: '', script: 'mvn install'
    }
    stage('Test')
    {
        sh label: '', script: '''cd */acceptance-tests 
        mvn clean verify 
        '''
    }
}