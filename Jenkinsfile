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
}
