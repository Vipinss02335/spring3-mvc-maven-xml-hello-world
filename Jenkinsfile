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
         
        stage('deploy') {
            steps {
                // Tomcat deploy
                    
                    sh "curl -v -u admin:adminadmin -T /var/lib/jenkins/workspace/spring3/target/spring3-mvc-maven-xml-hello-world-1.0-SNAPSHOT.war 'http://ec2-3-111-186-183.ap-south-1.compute.amazonaws.com:8080/manager/text/deploy?path=/vipn1&update=true'"
                              
               }    
           
            
           } 
         
        }

    
   }
