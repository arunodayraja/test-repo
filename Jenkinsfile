node {
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
   
  def message = sh 'git log -1' 
  echo message
  result = sh (script: "git log -1 | grep '\\[ci skip\\]'", returnStatus: true) 
  if (result != 0) {
    echo "performing build..."
    echo String.valueOf(result)
  } else {
    echo "not running..."
  }
   
   node {
 stage ("Skip build?") {
     result = sh (script: "git log -1 | grep '.*\\[ci skip\\].*'", returnStatus: true)
     if (result != 0) {
         echo ("This build should be skipped. Aborting.")
         env.shouldBuild = "false"
     } else {
        
     echo "not running..."
     
     }
 }

}
   
   
   
}

