node {
   
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
 def comm = 'roll status'
  BUILD_FULL = sh (returnStdout: true, script: 'git log --pretty=oneline -1 | cut -c 42- | head').trim()
  echo  BUILD_FULL
   
  if (BUILD_FULL.toUpperCase() == comm.toUpperCase())
   
   {
         echo ("This build should be skipped. Aborting.")
        echo ("Here the commit message not matched ")
         env.shouldBuild = "false"
     } else {
        
     echo "not running..."
        echo ("Here the commit message matched ")
     
     }
        
    }


