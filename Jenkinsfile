pipeline { 
    agent any 

    stages
    {
        stage ('Build')
        {
            steps
            {
                echo 'second-job'
                node {
   
    def server = Artifactory.server "SERVER_ID"
    
    def rtMaven = Artifactory.newMavenBuild()
    def buildInfo

    stage('Clone sources') {
        git url: 'https://github.com/VigneshThanthony/Pipeline_Test.git'
    }

    stage('Artifactory configuration') {
        
        rtMaven.tool = "Maven-3.8.4"
        
        rtMaven.deployer releaseRepo:'libs-release-local', snapshotRepo:'libs-snapshot-local', server: server
        rtMaven.resolver releaseRepo:'libs-release', snapshotRepo:'libs-snapshot', server: server
    }

    stage('Maven build') {
        buildInfo = rtMaven.run pom: 'maven-example/pom.xml', goals: 'clean install'
    }

    stage('Publish build info') {
        server.publishBuildInfo buildInfo
    }
}
            }
        }
        
        stage ('Test')
        {
            steps
            {
                echo 'third-job'
            }
        }
        
        stage ('Deploy')
        {
            steps
            {
                echo 'Deploy App'
            }
        }
    }
}
