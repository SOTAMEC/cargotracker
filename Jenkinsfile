Pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages {
        stages ('Build') {
            steps { 
                  sh script : 'mvn clean package'
            }       
        }
        stage('Upload war file to nexus') {
            steps{ nexusArtifactUploader artifacts: [
                       [
                          artifactId: 'cargo-tracker',
                          classifier: '', 
                          file: 'target/argo-tracker-1.0.war', 
                          type: 'war'
                        ]
                  ], 
                  credentialsId: 'Nexus-credentials',
                  groupId: 'net.java', 
                  nexusUrl: '75.101.188.209', 
                  nexusVersion: 'nexus3', 
                  protocol: 'http', 
                  repository: 'http://75.101.188.209:8081/repository/repository-example/', 
                  version: '1.0'
            }
         }
      }
   }      
            
            
            
