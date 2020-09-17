pipeline{
        agent any
        stages{
                stage('clone ChaperooToDoClient'){
                        steps{
                                sh "git clone https://gitlab.com/qacdevops/chaperootodo_client.git"
                        }
                }
                stage('Install Docker and Docker-Compose'){
                        steps{
                                sh "curl https://get.docker.com | sudo bash"
                                sh "sudo curl -L "https://github.com/docker/compose/releases/download/1.27.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose"
                        }
                }
                stage('Deploy Application'){
                        steps{
                                sh "sudo docker-compose up -d"
                        }
                }
        }
}
