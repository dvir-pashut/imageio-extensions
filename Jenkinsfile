pipeline{
    agent any
    
    tools {
    maven "some name"
    jdk "java ledugma"
    }

    stages{
        stage("checkout"){
            steps{
                echo "========checking out (loking hella fine)========"
                deleteDir()
                checkout scm 
            }
        }
        stage("build"){
            steps{
                echo "========executing A========"
                
                withMaven {
                    configFileProvider([configFile(fileId: '0a5edd42-4379-4509-a49e-d8ba1384edeb', variable: 'set')]) {
                        sh "mvn -s ${set} deploy"
                    } 
                } // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
                
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


