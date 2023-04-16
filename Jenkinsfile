@library('my-shared-library') _

pipeline {

    agent any

    stages {

        stage('Git checkout'){
            steps{
                script{
                    GitCheckout{
                        branch: "main",
                        url: "https://github.com/cdhlearning/Project-1.git"
                    }
                }
            }
        }
    }
}