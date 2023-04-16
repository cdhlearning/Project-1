@Library('my-shared-library') _

pipeline {

    agent any

    stages {

        stage('Git checkout'){
            steps{
                script{
                    gitCheckout(
                    branch: "main",
                    url: "https://github.com/cdhlearning/Project-1.git"
                    )
                }   
            }
        }
        stage('unit test maven'){
            steps{
                script{
                  mvntest()
                }   
            }
        }
    }
}