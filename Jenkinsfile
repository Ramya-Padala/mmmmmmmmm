pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
       git branch: 'main',
         url: "https://github.com/Ramya-Padala/static-website-cicd.git"
    }
  }
      stage('build') {
        steps {
        echo"building docker image"
        sh 'docker build -t httpd:v1 .'
      }
    }
      stage('deploy') {
        steps {
          echo 'Deploying Apache website...'
        sh 'docker run -d --name apache-website -p 8081:80 httpd:v1'
      }
    }    
  }
}
