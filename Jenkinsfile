node {
   
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
 def comm = 'roll snapshot'
  BUILD_FULL = sh (returnStdout: true, script: 'git log --pretty=oneline -1 | cut -c 42- | head').trim()
  echo  BUILD_FULL
   
  if (BUILD_FULL.toUpperCase() == comm.toUpperCase())
   
   {
         echo ("This build should be skipped. Aborting.")
       
     } else {
        
     
        echo ("Build should go on yes")
     
     }
        
    }


