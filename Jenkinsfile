pipeline {
  agent { label "Jenkins-Agent" }

  tools {
        jdk "Java17"
        maven "maven3"    
  }

  stages {
       stage ("Cleanup Workspace") {
         steps {
           cleanWs()           
         } 
       }

       stage ("Code Checkout") {
         steps {
            git branch: 'main', url: 'https://github.com/NKCloudDevOps/register-app'
                           
         }
       }

       stage ("Build Application") {
         steps {
            sh "mvn clean package"           
         }
       }

       stage ("Test Application") {
         steps {
           sh "mvc test"
         }
       }
   }
}
