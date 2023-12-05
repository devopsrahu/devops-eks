pipeline {
    agent any

   stages {
        /*stage('github') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/chanduooo/devops-eks.git']])
            }
        }*/
         stage('init') {
            steps {
                sh 'terraform init'
            }
        }
         stage('validate') {
            steps {
                sh 'terraform validate'
          }
        }
         stage('plan') {
            steps {
                sh 'terraform plan'
         }
    }
         stage('apply') {
            steps {
                sh 'terraform apply --auto-approve'
        }
     }
}
}

