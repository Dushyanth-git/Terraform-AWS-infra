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
                    sh 'terraform init'
                }

        }
        stage('plan'){
            steps{
                    sh 'terraform plan'
                }
            }
        stage('apply-approval'){
            steps{
                input "Apply Terraform changes?"
            }
        }
        stage('apply'){
            steps{ 
                    sh 'terraform apply -auto-approve'
                }
            }
        }
    }
