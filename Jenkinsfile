node {
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
   
   echo sh 'git log --oneline -1 ${GIT_COMMIT}'
   
   
   
   def message3 = sh 'git log --pretty=oneline -1 | cut -c 42- | head'
   echo message3
   
   
   String str = "roll snapshot" 
   def str2 = message3 
  if( str2.toUpperCase() == str.toUpperCase() ) { 
    println "same" 
  }else{ 
    println "not same" 
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


