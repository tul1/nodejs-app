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
          ./terraform --version
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
        // script {
        def shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
        // }

        sh "echo $shortCommit"
        // withCredentials([string(credentialsId: 'ecr_credential', variable: 'ECR_CREDENTIAL')]) {
        //     sh """
        //       docker build -t 927291680788.dkr.ecr.eu-west-1.amazonaws.com/myapp:${TAG} .
        //       docker login 
        //       docker push 927291680788.dkr.ecr.eu-west-1.amazonaws.com/myapp:${TAG}
        //     """
        // }
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