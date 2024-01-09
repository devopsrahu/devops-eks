pipeline {
    agent any

   stages {
       steps {
            withCredentials([usernamePassword(credentialsId: 'AKIAU5WM3DC6V2YAHJOQ', accessKeyVariable: 'AWS_ACCESS_KEY_ID', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY')]) {
                sh 'echo $AWS_ACCESS_KEY_ID'
                sh 'echo $AWS_SECRET_ACCESS_KEY'
            }
      }
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
        stage('destroy') {
            steps {
                sh 'terraform destroy --auto-approve'
        }
      }
}
}
