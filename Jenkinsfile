pipeline {
    agent {label 'windows'}
    stages {
        stage('build') {
            steps {
                script {
                    echo "************** Creating Python 2.7 virtual Environment *******************"
                    echo "**** Checking if pyvenvs directory exist ****"
                    if(!fileExists("\pyvenvs"))
                    {
                        echo bat(returnStdout: true, script: 'mkdir pyvenvs')
                    }else{
                        echo "Directory pyvenvs alredy exists"
                    }
                    echo "**** Installing and upgrading pip ****"
                    echo bat(returnStdout: true, script: 'python -m pip install --upgrade pip')   
                        
                        
                    //echo "************** Creating Python 2.7 virtual Environment *******************"
                    //echo bat(returnStdout: true, script: 'mkdir pyvenvs')
                    //echo env.PATH
                    //echo bat(returnStdout: true, script: 'python -m pip install --upgrade pip')
                    
                    
                    
                }
            }
        }
        stage('test') {
            steps {
                script {
                   echo "************** Testing code *******************"
                }
            }
        }
    }
}
