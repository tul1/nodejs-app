def TERRAFORM = ".//var/jenkins_home/workspace/node-app_master/terraform"
pipeline {
  agent { 
    docker { image 'node' }
  }
  stages {
    stage('Setup environment') {
      steps {
        sh """
          wget https://releases.hashicorp.com/terraform/0.12.24/terraform_0.12.24_linux_amd64.zip
          echo y | unzip terraform_0.12.24_linux_amd64.zip
          pwd
          ${TERRAFORM} --version
        """
      }
    }
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
        sh """
          ./${TERRAFORM} --version
        """
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