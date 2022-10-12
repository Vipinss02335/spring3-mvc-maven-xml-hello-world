pipeline {
agent any
      
   stages {
        stage ('SCM') {
            steps {
                 git credentialsId: 'github_credentials1', url: 'https://github.com/Ratheesh1986/spring3-mvc-maven-xml-hello-world.git'
                }
           }
        stage ('Build') {
            steps {
                 sh "mvn -Dmaven.test.failure.ignore=true clean package"
                }
           }
           
        stage ('Artifacts') {
            steps {
                
                 archiveArtifacts 'target/*.war'
                }
           }
         
           
           } 
         
        }

    
   }
