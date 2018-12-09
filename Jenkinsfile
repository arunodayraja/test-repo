node {
   
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
 checkout scm
 
   sh 'git log --oneline -1 ${GIT_COMMIT}'
   sh 'git log --pretty=oneline -1 | cut -c 42- | head'
   
   
   gitCommit = sh(returnStdout: true, script: 'git rev-parse HEAD').toString().trim()

   
   GIT_COMMIT_EMAIL = sh (script: 'git --no-pager show -s --format=\'%ae\'', returnStdout: true).trim()
   
   echo "Git committer email: ${GIT_COMMIT_EMAIL}"
   
   
   
   echo gitCommit
   echo GIT_COMMIT_EMAIL
   
   
  
        
    }


