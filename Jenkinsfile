//def gv                                    //just adding this part to test the webhook trigger

pipeline {
    agent any
    stages {
        stage("build") {
            steps {
                echo 'building the application'
        //stage("init") {
         //   steps {
          //      script {
           //         gv = load "script.groovy"
            //    }
            }
        }
        stage("build jar") {
            steps {
                script {
                    echo "building jar"
                    //gv.buildJar()
                }
            }
        }
        stage("build image") {
            steps {
                script {
                    echo "building image"
                    //gv.buildImage()
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    echo "deploying"
                    //gv.deployApp()
                }
            }
        }
    }   
}
