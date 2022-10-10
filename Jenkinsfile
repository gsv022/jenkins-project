pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }
  
    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing.........'

            }
        }
        
        // Stage3: Publish to Nexus
        stage ('Publish to Nexus'){
            steps {
         nexusArtifactUploader artifacts: [[artifactId: 'DevopsLab', classifier: '', file: 'target/venkat_devops.war', type: 'war']], credentialsId: '1114d17c-c923-4b07-8121-a23ce4f71d17', groupId: 'com.devopslab', nexusUrl: '44.200.162.163:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'venkat_devops', version: '0.0.14-SNAPSHOT'
            }
        }

       // Stage4 : Deploying
        stage ('Deploy'){
            steps {
                echo ' Deploying......'

            }
        }


//stages
    }

}
