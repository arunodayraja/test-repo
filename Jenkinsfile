node {
   
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
 
   sh 'git log --oneline -1 ${GIT_COMMIT}'
   sh 'git log --pretty=oneline -1 | cut -c 42- | head'
   
   
   gitCommit = sh(returnStdout: true, script: 'git rev-parse HEAD').toString().trim()
   commitChangeset = sh(script: 'ls -al', returnStdout: true)
   
   echo gitCommit
   echo commitChangeset
   
   
  
        
    }


