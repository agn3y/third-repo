def gv

pipeline {
    agent any

    tools {
        maven 'maven-latest'
    }

    environment {
        IMAGE_NAME = 'agneypatel/test-repoo:1.4'
    }

    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }

        stage("Build JAR") {
            steps {
                script {
                    gv.buildJar()
                }
            }
        }

        stage("Build Docker Image") {
            steps {
                script {
                    gv.buildImage()
                }
            }
        }

        stage("Deploy") {
            steps {
                script {
                    gv.deployApp()
                    // Add your deploy commands here
                }
            }
        }
    }
}

