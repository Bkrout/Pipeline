node('master')
{
    stage('ContinousDownload')
    {
    git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage('ContinousBuild')
    {
    sh label: '', script: 'mvn package'
    }
    stage('ContinousDeployment')
    {
    sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.16.56:/var/lib/tomcat8/webapps/testapp.war'
    }
    stage('ContinousTesting')
    {
    git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
    sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/Scriptedpipeline/testing.jar'
    }
    stage('ContinousDelivery')
    {
    sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.28.143:/var/lib/tomcat8/webapps/testapp.war'
    }
}
