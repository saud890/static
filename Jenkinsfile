pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps { 
          withAWS(credentials: 'aws-credentials', region: 'eu-west-1') {
              sh 'echo "Hello World"'
              sh '''
              s3Upload(file:'index.html', bucket:'saudbucket', path:'path static/index.html')
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
      }
    }
    }
  }
}
