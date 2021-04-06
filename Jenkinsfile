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
            sh 'mvn compile'
}
      }
      
  }
    stage('please test code')
    {
      steps{
          withMaven(jdk: 'localjdk-1.8', maven: 'localmaven') {
            sh 'mvn test'
}
      }
    }
}
