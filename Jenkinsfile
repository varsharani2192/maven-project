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
        stage (archive the artifact)
        {
            steps{ archiveArtifacts artifacts: '**/*.war', followSymlinks: false}
        }
        stage ( deploy to container)
        {
            steps{
                deploy adapters: [tomcat7(credentialsId: 'tomcat', path: '', url: 'http://18.220.127.6/')], contextPath: '/var/lib/tomcat/webapps', war: '**/*.war'
            }
        }
    }
}
