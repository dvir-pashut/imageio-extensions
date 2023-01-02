pipeline{
    agent any
    
    tools {
    maven 'Maven 3.6.3'
    }

    stages{
        stage("A"){
            steps{
                echo "========executing A========"
                sh 'mvn clean package'
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