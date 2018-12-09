node {
   
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
 
       
   BUILD_FULL = sh (returnStdout: true, script: 'git log --pretty=oneline -1 | cut -c 42- | head').trim()

      
   
   echo  BUILD_FULL
  
        
    }


