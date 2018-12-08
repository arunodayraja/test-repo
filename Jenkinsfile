node {
   echo 'Hello World'
   git credentialsId: 'git-login', url: 'https://github.com/arunodayraja/test-repo'
}
node {
  checkout scm
  result = sh (script: "git log -1 | grep '\\[ci skip\\]'", returnStatus: true) 
  if (result != 0) {
    echo "performing build..."
    echo git log -1 
  } else {
    echo "not running..."
  }
}
