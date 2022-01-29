pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
               git branch: 'main', url: 'https://github.com/DiSwami/EduDevOpsTest.git'
            }
        }
        stage('Docker Build'){
            steps{
                sh "docker build . -t dswami0312/my-php-website"
            }
        }
        stage('DockerHub Push'){
            steps{
                
               withCredentials([string(credentialsId: 'DockerPwd', variable: 'dockerpwd')]) { 

                        sh "docker login -u dswami0312 -p ${dockerpwd}"

} 
                
                sh "docker push dswami0312/my-php-website "
            }
        }
        
         stage('Install docker and its dependencies and run contianer') {
            steps {
               ansiblePlaybook credentialsId: 'ansibleconn', installation: 'Ansible 2.9.27', inventory: 'servers.inv', playbook: 'deployment-playbook.yml' 
            }
        }
    }
}

