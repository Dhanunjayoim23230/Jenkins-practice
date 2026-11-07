pipeline{
    agent {label 'AGENT-1'}
        stages{
            stage('build'){
                steps{
                    sh """
                    echo "hello this is build"

                    """
                }
            }
            stage('test'){
                steps{
                    sh """
                    echo " hello this is test"
                    kjhfhkgf
                    """
                }
            }
            stage('deploy'){
                steps{
                    sh """
                    echo " hello this is deploy"
                    """
                }
            }
        }
        post { 
        always { 
            echo 'I will always say Hello again!'
        }
         failure { 
            echo 'I will run when pipeline is failed!'
        }
         success { 
            echo 'I will run when pipeline is success'
        }
    }
}
