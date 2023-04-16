pipeline {

    agent any

    stages {

        stage('Git checkout'){
            steps{
                script{
                    git branch: 'main', url: 'https://github.com/cdhlearning/Project-1.git'
                }
            }
        }
    }
}