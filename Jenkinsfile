pipeline{
        agent any
        stages{
                stage('Make Directory'){
                        steps{
                                sh "mkdir ~/jenkins-pipeline"
                        }
                }
                stage('Make Files'){
                        steps{
                                sh "touch ~/jenkins-pipeline/file1.txt ~/jenkins-pipeline/file2.txt"
                        }
                }stage('List Files'){
                        steps{
                                sh "ls -al"
                        }
                }
        }
}
