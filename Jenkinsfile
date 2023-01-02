pipeline{
    agent any
    
    tools {
    maven "some name"
    }

    stages{
        stage("A"){
            steps{
                echo "========executing A========"
                
                configFileProvider([configFile(fileId: 'MyGlobalSettings', variable: 'set')]) {
                sh "mvn -s ${set} install"
                } 
                
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}


