node {
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
   
   sh 'git log --oneline -1 ${GIT_COMMIT}'
   sh 'git log --pretty=oneline -1 | cut -c 42- | head'
   
   
   def message3 = sh 'git log --pretty=oneline -1 | cut -c 42- | head'
   echo message3
   
   
   // Test commit message for flags
def BUILD_FULL = sh (script: "git log -1 --pretty=%B | grep '\\[roll snapshot]'", returnStatus: true) == 0
   
echo "Build full flag: ${BUILD_FULL}"
   
   def value = echo "${BUILD_FULL}"
   
   echo value
   
   if (BUILD_FULL == false) {
      
                    echo ("'ci skip' spotted in git commit. Aborting.")
                    shouldBuild = "false"
                } else {
        
     echo "not running..."
        echo ("Here the commit message matched and skipping and changed the code ")
     
     }
   
   
   
   
    
   def message = sh 'git log -1' 
   echo message
   
   
   node {
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
        echo ("Here the commit message matched and skipping and changed the code ")
     
     }
            }
        }

}
   
    }


