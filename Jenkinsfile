pipeline{
    agent any
    stages{
        stage ('clone the repo')
        {
            steps{ git branch: 'master', url='https://github.com/santoshdeshmane06/maven-project.git'}
        }
        stage ('Build teh package')
        {
            steps{ 
                withMavenwithMaven(jdk: 'locakjdk', maven: 'localmaven') 
                {
                    sh 'mvn package'
                }
                }
        }
    }
}
