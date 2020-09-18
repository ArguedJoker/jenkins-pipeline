pipeline{
        agent any
        stages{
                stage('clone ChaperooToDoClient'){
                        steps{
                                sh "cd chaperootodo_client || git clone https://gitlab.com/qacdevops/chaperootodo_client"
                        }
                }
                stage('Install Docker and Docker-Compose'){
                        steps{
                                sh '''
                                curl https://get.docker.com | sudo bash
                                curl -L "https://github.com/docker/compose/releases/download/1.27.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
                                chmod +x /usr/local/bin/docker-compose '''
                        }
                }
                stage('Deploy Application'){
                        steps{
                                sh "docker-compose up -d"
                        }
                }
        }
}
