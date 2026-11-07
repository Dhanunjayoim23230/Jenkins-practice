# Jenkins practice #


* 1 Check the storage *
* 2 If required increase the storage *
* 3 Install java 17 or 21 version *
* 4 Install jenkins *
```
dnf install jenkins -y
```

```
systemctl enable jenkins -y
```

```
systemctl start jenkins -y
```


## sample pipeline code  DSL(Domain Specific Language)##
```
pipeline{
    agent {label 'AGENT-1'}
    environment { 
        project = 'expense'
        component = 'backend'
        name = 'dhanunjaya reddy'
        DEPLOY_TO = 'QA'
    }
    options { 
        disableConcurrentBuilds() 
        // timeout(time: 5, unit: 'SECONDS')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    } 
        stages{
            stage('build'){
                steps{
                    script{
                        sh """
                        echo "hello this is build"
                        echo " Project name is : $name"
                        """
                    }
                    
                }
            }
            stage('test'){
                steps{
                    script{
                        sh """
                        echo " hello this is test"
                        """
                    }
                    
                }
            }
            stage('deploy'){
                /* input {
                    message "Should we continue?"
                    ok "Yes, we should."
                    submitter "Dhanunjaya reddy"
                    parameters {
                        string(name: 'PERSON', defaultValue: 'Mr Dhanunjaya reddy', description: 'Who should I say hello to?')
                    }
                } */
                // when { branch 'main' }
                when { environment name: 'DEPLOY_TO', value: 'QA' 
                }
                steps{
                    script{
                        sh """
                            echo " hello this is deploy"
                            """
                    }                   
                }
            }
            stage('Parallel stages') {
                    parallel {
                        stage('STAGE-1') {
                            steps {
                                script{
                                    sh """
                                    echo "In Parallel STAGE - 1"
                                    sleep 15
                                    """
                                }                                
                            }
                        }
                        stage('STAGE-2') {
                            steps {
                                script{
                                    sh """
                                    echo "In Parallel STAGE - 2"
                                    sleep 15
                                    """
                                }                                 
                            }
                        }
                    }
                }
        }
        post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
         failure { 
            echo 'I will run when pipeline is failed!'
        }
         success { 
            echo 'I will run when pipeline is success'
        }
    }
}

```