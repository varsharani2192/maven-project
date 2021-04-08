pipeline
{
  agent any
  stages
  {
      stage('scm checkout')
        {
          steps{
             git branch: 'master', url: 'https://github.com/varsharani2192/maven-project'
              }
        }
        stage('please compile code')
    {
      steps{
          withMaven(jdk: 'localjdk-1.8', maven: 'localmaven') {
            sh 'mvn compile'}
           }     
    }
    stage('please test code')
    {
      steps{
          withMaven(jdk: 'localjdk-1.8', maven: 'localmaven') {
            sh 'mvn test'}
          }
     }
    stage('please build code')
    {
      steps{
          withMaven(jdk: 'localjdk-1.8', maven: 'localmaven') {
            sh 'mvn package'}
          }
     }
    
    stage('deploy to tomcat')
           {
            steps
                {
                    sshagent(['f61345e7-1fe8-40c2-b264-74a7fc33c1f9']) {
                    sh 'ssh -o StrictHostKeyChecking=no */target/webapp.war ec2-user@172.31.24.68:/var/lib/tomcat/webapps'}
                }
          }
    }
  
}
}
