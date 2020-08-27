pipeline {
    agent {label 'windows'}
    stages {
        stage('build') {
            steps {
                script {
                    if(!fileExists("\\pyvenvs"))
                    {
                        echo bat(returnStdout: true, script: 'mkdir pyvenvs')
                    }else{
                        echo "Directory exists"
                    }
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
