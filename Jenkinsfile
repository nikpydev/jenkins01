pipeline{
    agent{
        label "node"
    }
    tools{
        nodejs 'NodeJS-01'
    }
    stages{
        stage("A"){
            steps{
                echo "========executing A========"
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
        stage("B"){
            steps{
                echo "========executing B========"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========B executed successfully========"
                }
                failure{
                    echo "========B execution failed========"
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