node {
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
   
  def message = sh 'git log -1' 
  echo message
   
   
   node {
 stage ("Skip build?") {
     result = sh (script: "git log -1 | grep '.*\\[ci skip\\].*'", returnStatus: true)
     if (result != 0) {
         echo ("This build should be skipped. Aborting.")
        echo ("Here the commit message doesn't matched ")
         env.shouldBuild = "false"
     } else {
        
     echo "not running..."
        echo ("Here the commit message matched ")
     
     }
 }

}
    
}

