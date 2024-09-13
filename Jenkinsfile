pipeline {
  agent { label "Jenkins-Agent" }

  tools {
        Java "openjdk"
        Maven "maven3"    
  }

  stages {
       stage (Cleanup Workspace)
         steps {
           cleanws()           
         } 

       stage (Code Checkout)
         steps {
            git branch: 'main', credentialsid: 'github', url: 'https://github.com/NKCloudDevOps/register-app'
                            
         }

       stage (Build Application)
         steps {
            sh "mvn clean package"           
         }

       stage (Test Application)
         steps {
           sh "mvc test"
         }
    
  }











}
