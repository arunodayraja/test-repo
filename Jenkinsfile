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
     result = sh (script: "git log -1 | grep '\\[ci skip\\]'", returnStatus: true)
    echo result.toString()
     if (result == 0) {
         echo ("This build should be skipped. Aborting.")
        echo ("Here the commit message not matched ")
         env.shouldBuild = "false"
     } else {
        
     echo "not running..."
        echo ("Here the commit message matched ")
     
     }
 }

}
    stage ("Checkout SCM") {
        
            script {
                checkout scm
                result = sh (script: "git log -1 | grep '.*\\[ci skip\\].*'", returnStatus: true) 
               echo result.toString()
                if (result == 0) {
                    echo ("'ci skip' spotted in git commit. Aborting.")
                    shouldBuild = "false"
                } else {
        
     echo "not running..."
        echo ("Here the commit message matched ")
     
     }
            }
        }
    }


