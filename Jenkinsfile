@Library('My_Library') _

pipeline {
    agent any

    stages {
        stage('Codecheckout') {
            steps {
                script {
                    cicd.gitdownload("maven")
                }
            }
        }
            stage('codebuild') {
                steps {
                    script {
                        cicd.gitbuild()
                
                }
            }
        }
        stage('contdeploy') {
            steps {
                script {
                    cicd.gitdeploy("Scriptedvars","43.204.148.217","testapp")
                }
            }
        }
        stage('conttest'){
            steps{
                script{
                    cicd.gitdownload("FunctionalTesting")
                    cicd.gittest("Scriptedvars")
                }
            }
        }
        stage('contDeliver'){
            steps{
                script{
                    cicd.gitdeploy("Scriptedvars","43.204.148.217","prodapp")
                }
            }
        }
    }
}
