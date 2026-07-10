pipeline{

    agent any

            tools{

                maven 'Maven-3.9.12'
                jdk 'JDK17'
            }

            environment{
                APP_NAME = 'localhelp'
                COMPANY = 'local'
            }

            parameters{
                    choice(
                        name: 'ENV',
                        choices: ['dev','stage','uat','prod'],
                        description: 'Select Environment'
                    )

                    string(
                        name: 'VERSION',
                        defaultValue: '1.0.0',
                        description: 'Application Version'
                    )
            }
            stages{

                stage('Pipeline Info'){
                    steps{

                        echo "Job Name : ${env.JOB_NAME}"
                        echo "Build Number : ${env.BUILD_NUMBER}"

                        echo "App Name : ${APP_NAME}"
                        echo "Company : ${COMPANY}"

                        echo "Environment : ${params.ENV}"
                        echo "Version : ${params.VERSION}"

                        sh '''
                            echo "=======SHELL========"
                            echo "JOB=$JOB_NAME"
                            echo "BUILD=$BUILD_NUMBER"

                            echo APP=$APP_NAME
                            echo COMPANY=$COMPANY

                            echo ENV=$ENV
                            echo VERSION=$VERSION

                            java -version
                            mvn -version

                          '''
                    }
                }
            

            }
}