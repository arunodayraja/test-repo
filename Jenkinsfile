node {
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
   
  
  echo  'git', 'log', "--pretty=format:* %h: %s"

  checkout scm
  result = sh (script: "git log -1 | grep '\\[ci skip\\]'", returnStatus: true) 
  if (result != 0) {
    echo "performing build..."
    echo String.valueOf(result)
  } else {
    echo "not running..."
  }
}
