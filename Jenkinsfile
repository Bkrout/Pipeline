node('master')
{
    stage('ContinousDownload-master')
    {
    git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage('ContinousBuild-master`')
    {
    sh label: '', script: 'mvn package'
    }
    
}
