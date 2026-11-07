pipeline{
    agent {label 'AGENT-1'}
    environment { 
        project = 'expense'
        component = 'backend'
    }
    options { 
        disableConcurrentBuilds() 
    } 
        stages{
            stage('build'){
                steps{
                    sh """
                    echo "hello this is build"
                    echo " Project name is : $project"
                    sleep 30

                    """
                }
            }
            stage('test'){
                steps{
                    sh """
                    echo " hello this is test"
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
