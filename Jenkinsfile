@Library('my-shared-library') _

pipeline {

    agent any

    parameters{

        choice(name: 'action', choices: 'create\ndelete', description: 'choose create or delete')
    }

    stages {

        stage('Git checkout'){
            when{ expression { params.action == 'create' } }
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
            when { expression { params.action == 'create' } }
            steps{
                script{
                  mvntest()
                }   
            }
        }
        stage('integration test Maven'){
            when { expression { params.action == 'create'}}
            steps{
                script{
                  mvnintegrationtest()
                }   
            }
        }
        stage('static code analysis Sonarqube'){
            when { expression { params.action == 'create'}}
            steps{
                script{
                    def SonarQubecredentialId = 'sonar'
                    staticodeanalysis(SonarQubecredentialId)
                }
            }
            
        }

        stage('iqaulity gate status check'){
            when { expression { params.action == 'create'}}
            steps{
                script{
                    def SonarQubecredentialId = 'sonar'
                    qualityGate(SonarQubecredentialId)
                }   
            }
        }
    }
}
