node {
   
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
 
   sh 'git log --oneline -1 ${GIT_COMMIT}'
   sh 'git log --pretty=oneline -1 | cut -c 42- | head'
   
sh 'echo (sh 'git log --pretty=oneline -1 | cut -c 42- | head') > result'
def output=readFile('result').trim()
echo output
   
   
   
  
        
    }


