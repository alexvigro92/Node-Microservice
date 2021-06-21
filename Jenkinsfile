pipeline {
    agent any

    stages {
        stage("Build"){
            agent {
              docker 'node:12.16.1'
            }
            steps {
                sh 'npm help'
            }
        }

        stage("Test"){
            steps {
                sh 'echo "run tests"'
            }
        }

        stage("Deploy"){
            agent { 
                docker {
                   image 'ibmcom/ibm-cloud-developer-tools-amd64'
                   args '-u root'
                }
            }
            steps {
                sh 'ibmcloud --help'
            }
        }

    }
}
