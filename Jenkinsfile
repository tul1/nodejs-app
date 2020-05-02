pipeline {
  agent { 
    docker { image 'node' }
  }
  stages {
    stage('Lint ') {
    steps {
      sh "npm run lint"
    }
  }
  stage('tests') {
    steps {
      sh "npm run test"
    }
  }
  stage('Build Docker image and push it into AWS') {
    steps {
      //Push image into AWS registry
    }
  }
  stage('Create Infrastructure and deploy app') {
    steps {
      // Terraform commands to create app infra
      //Push image into AWS registry
    }
  }
}
