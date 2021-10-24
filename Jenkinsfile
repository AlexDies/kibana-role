pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Git Check') {
            steps{
                git branch: 'kibana_role(molecule)', credentialsId: '555e5b54-c114-4c38-92a4-07a3f0bc647c', url: 'git@github.com:AlexDies/kibana-role.git'
            }
        }
        stage('Install molecule') {
            steps{
                sh 'pip3 install molecule-docker'
                sh 'pip3 install -r test-requirements.txt' 
            }
        }
        stage('Run Molecule') {
            steps{
                sh 'molecule test'
            }
        }    
        
    }
}
