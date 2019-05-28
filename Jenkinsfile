node {
  try {     
    stage('Preparation') { 
      git branch: 'master', uri: 'https://github.com/eugeny777/build_flask_app'
    }
    stage('Build') {
      sh 'docker build -t evheny777/flask_app:${BUILD_NUMBER}  .'
    }
    stage ('Push to registry'){
      sh 'docker login -u "evheny777" -p ""' && 'docker push evheny777/flask_app:${BUILD_NUMBER}'
    }

  }
  catch(e) { 
    currentBuild.result = "FAILED"
    throw e
  }
}  
