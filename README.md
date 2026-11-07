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


## sample pipeline code ##
```
pipeline{
    agent any
        stages {
            stage('build'){
                    steps{
                        script{
                            sh " " "
                            echo "hello this is build"
                            " " "
                        }
                    }
            }
            stage('test"){
                    steps{
                        script{
                            sh " " "
                            echo " hello this is test"
                            " " "
                        }
                    }
            }
            stage('deploy'){
                    steps{
                        sh " " "
                        echo " hello this is deploy"
                        " " "
                    }
            }
        }
}
```