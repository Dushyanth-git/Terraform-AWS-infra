pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('init') {
            steps{
                dir('terraform'){
                    sh 'terraform init'
                }
            }

        }
        stage('plan'){
            steps{
                dir('terraform'){
                    sh 'terraform plan'
                }
            }
        }
        stage('apply-approval'){
            steps{
                input "Apply Terraform changes?"
            }
        }
        stage('apply'){
            steps{
                dir('terraform'){
                    sh 'terraform apply -auto-approve'
                }
            }
        }
    }
}