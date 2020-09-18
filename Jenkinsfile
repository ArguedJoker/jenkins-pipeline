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
                                sudo curl -L "https://github.com/docker/compose/releases/download/1.27.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
                                sudo chmod +x /usr/local/bin/docker-compose 
                                '''
                        }
                }
                stage('Deploy Application'){
                        steps{
                                sh "sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d"
                        }
                }
        }
}
