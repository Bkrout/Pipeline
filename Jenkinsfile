pipeline
{
    agent any
    stages
    {
        stage(ContinosDownload)
        {
            steps
            {
                git 'https://github.com/Bkrout/Pipeline.git'
            }
        }
        stage(ContinosBuild)
        {
            steps
            {
               sh label: '', script: 'mvn package'
            }
        }
         stage(ContinosDeployment)
        {
            steps
            {
               sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@172.31.16.56:/var/lib/tomcat8/webapps/testapp.war'
            }
        }
        stage(ContinosTesting)
        {
            steps
            {
               git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
               sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/Scriptedpipeline/testing.jar'
            }
        }
         stage(ContinosDelivery)
        {
            steps
            {
                 sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.28.143:/var/lib/tomcat8/webapps/testapp.war'
            }
        }
        
         
        
    }
}
