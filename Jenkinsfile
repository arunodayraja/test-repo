node {
   
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
   def result
   sh 'git log --oneline -1 ${GIT_COMMIT}'
   sh 'git log --pretty=oneline -1 | cut -c 42- | head'
   
sh "echo sh 'git log --pretty=oneline -1 | cut -c 42- | head' > result";
def output=readFile('result').trim()
echo output
   
   
   
   if (true == true) {
      
                    echo ("'ci skip' spotted in git commit. Aborting.")
                    shouldBuild = "false"
                } else {
        
     echo "not running..."
        echo ("Here the commit message matched and skipping adding ")
     
     }
        
    }


