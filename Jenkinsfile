//!/usr/bin/env groovy                                                     //added this line to test webhook trigger

//pipeline {
//    agent none
//    stages {
//        stage('build') {
//            steps {
//                script {
//                    echo "Building the application..."
//                }
//            }
//        }
//        stage('test') {
//            steps {
//                script {
//                    echo "Testing the application..."
//                }
//            }
//        }
//        stage('deploy') {
//            steps {
//                script {
//                    echo "Deploying the application..."
//                }
//            }
//        }
//    }
//}
pipeline {
    agent any
    stages {
        stage('test') {
            steps {
                script {
                    echo "Testing the application..."
                    echo "Executing pipeine for branch $BRANCH_NAME"
                }
            }
        }
        stage('build') {
            when {
                expression {
                    BRANCH_NAME == 'master'
                }
            }
            steps {
                script {
                    echo "Building the application..."
                }
            }
        }
        stage('deploy') {
            steps {
                script {
                    def dockerCmd = 'docker run -p 8083:80 krishank06/nginx-image:latest'
                    sshagent(['624a0a80-5d8b-4717-9881-0c52d005378a']) {
                        sh "ssh -o StrictHostKeyChecking=no ec2-user@3.110.136.161 ${dockerCmd}"
                    } 
                    echo "Deploying the application..."
                }
            }
        }
    }
}
