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
                    echo "**** Installing and upgrading pip ****"
                    echo bat(returnStdout: true, script: 'python -m pip install --upgrade pip')
                    echo bat(returnStdout: true, script: 'pip install virtualenv')
                    echo bat(returnStdout: true, script: 'cd pyvenvs')  
                    echo "**** Creating virtual environment for Python 3 ****" 
                    echo bat(returnStdout: true, script: 'cd pyvenvs && virtualenv py38venv') 
                    //echo "**** Creating virtual environment for Python 2 ****" 
                    //echo bat(returnStdout: true, script: 'cd pyvenvs && virtualenv -p C:\\Python27\\python.exe py27venv')
                    echo "**** Activating virtual environment for Python 3 and showing Python version ****"  
                    echo bat(returnStdout: true, script: 'cd pyvenvs && py38venv\\Scripts\\activate && python -V') 
                    //echo "**** Activating virtual environment for Python 2 ****"  
                    //echo bat(returnStdout: true, script: 'cd pyvenvs && py27venv\\Scripts\\activate && python -V')
                    //echo bat(returnStdout: true, script: 'cd pyvenvs && py38venv\\Scripts\\deactivate')  

                        
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



