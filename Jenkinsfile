pipeline{
    agent any

    environment{
        NEW_VARIABLE = 'cool variable'
    }

    stages{
        stage ("build"){
            steps{
               echo 'building the application...' 
               echo "${NEW_VARIABLE}"
            }
        }

        stage ("test"){
            when{
                expression{
                    BRANCH_NAME == 'main' || BRANCH_NAME == 'master'
                }
            }
            steps{
               echo 'testing the application...' 
            }
        }

        stage ("deploy"){
            steps{
               echo 'deploying the application...' 
            }
        }
    }
    post{
        success{
            echo 'pipeline succeeded'
        }
        failure{
            echo 'pipeline failed'
        }
    }
}