pipeline{
    agent any
    tools {nodejs "node"}
    stages{
        stage('git checkout'){
        steps {
            script{
                
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GITHUB_CREDENTIAL', url: 'https://github.com/paulfatoki/node-app-pipeline-project.git']])
                }


            }

        }
        stage('installing npm'){
        steps {
            script{
                sh 'npm install'

            }
        }
        

    }
}
}
        








