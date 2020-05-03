pipeline {
  agent { 
    docker { image 'node:stretch-slim' }
  }
  stages {
    stage('Install project dependencies') {
      steps {
        sh "npm install"
      }
    }
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
        sh "echo push to registry"
        //Push image into AWS registry
      }
    }
    stage('Create Infrastructure and deploy app') {
      steps {
        sh "echo create infra"
        // Terraform commands to create app infra
        //Push image into AWS registry
      }
    }
  }
}