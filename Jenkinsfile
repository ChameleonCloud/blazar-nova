pipeline {
  agent any
 
  options {
    copyArtifactPermission(projectNames: 'nova*')
  }

  stages {
    stage('package') {
      steps {
        dir('dist') {
          deleteDir()
        }
        sh 'python setup.py sdist'
        sh 'find dist -type f -exec cp {} dist/blazar-nova.tar.gz \\;'
        archiveArtifacts(artifacts: 'dist/blazar-nova.tar.gz', onlyIfSuccessful: true)
      }
    }
  }
}

