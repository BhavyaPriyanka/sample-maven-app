pipeline{

    agent any

    stages{

        stage('Checkout'){

            steps{

                 git 'https://github.com/BhavyaPriyanka/sample-maven-app.git'

            }
        }

        stage('Build'){

            steps{

                sh 'mvn clean package'
            }
        }

        stage('Archive'){

            steps{

                 archiveArtifacts artifacts: 'target/*.jar'
            }
        }



    }
}