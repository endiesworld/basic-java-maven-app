def gv

pipeline {   
    agent any
    tools {
        maven 'maven-3.9.11'
    }
    stages {
        stage("init") {
            steps {
                script {
                    echo "Projecet initialization..."
                    gv = load "script.groovy"
                }
            }
        }
        stage("build jar") {
            steps {
                script {
                    echo "Build project java app..."
                    gv.buildJar()

                }
            }
        }

        stage("build image") {
            steps {
                script {
                    gv.buildImage()
                }
            }
        }

        stage("deploy") {
            steps {
                script {
                    gv.deployApp()
                }
            }
        }               
    }
} 
