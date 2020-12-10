pipeline{
    agent any
    stages{
        stage ('clone the repo')
        {
            steps{ git url:'https://github.com/santoshdeshmane06/maven-project.git'}
        }
        stage ('Build teh package')
        {
            steps{ 
               withMaven(jdk: 'locakjdk', maven: 'localmaven') 
                {
                    sh 'mvn package'
                }
                }
        }
    }
}
