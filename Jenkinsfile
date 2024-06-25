pipeline{
    agent any
    tools {nodejs "node"}
    stages{
        stage('git checkout')
        steps {
            script{
                sh 'echo' 'git cloning'
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GITHUB_CREDENTIALS', url: 'https://github.com/paulfatoki/node-app-pipeline-project.git']])

            }


        }

        stage('installing npm')
        steps {
            script{
                sh 'npm install'
                
            }


        }
        stage('docker build')
        steps {
            script{
                sh 'docker build -t paulfatoki/reactapp .'
                
            }


        }







    }
        stage('pushing docker image to dockerhub')
        steps {
            script{
                withCredentials([string(credentialsId: 'dockerhub_ID', variable: 'dockerhub_ID')]) {
                sh 'docker login -u paulfatoki -p ${dockerhub_ID}'
                sh 'docker push paulfatoki/reactapp:latest' 
                    }
                
            }


        }







    }








