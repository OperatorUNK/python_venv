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
                    echo "Workspace is ${WORKSPACE}"
                    //Workspace is C:\jenkins\workspace\python_test\python_venv_pipeline

                    echo "**** Creating virtual environment for Python 3 ****" 
                    echo bat(returnStdout: true, script: 'cd pyvenvs && virtualenv py38venv')

                    echo "**** Activating virtual environment for Python 3 and showing Python version ****"

                    echo bat(returnStdout: true, script: 'cd pyvenvs && py38venv\\Scripts\\activate && python -V && C:\\jenkins\\workspace\\python_test\\python_venv_pipeline\\test_py3\\Hello_python3.py')
                    

                    echo "**** Deactivating virtual environments Python 3 ****"
                    echo bat(returnStdout: true, script: 'cd pyvenvs && py38venv\\Scripts\\deactivate')
                    

                    //echo "**** Creating virtual environment for Python 2 ****" 
                    //echo bat(returnStdout: true, script: 'cd pyvenvs && virtualenv -p C:\\Python27\\python.exe py27venv')

                    //echo "**** Activating virtual environment for Python 2 ****"
 
                    //echo bat(returnStdout: true, script: 'cd pyvenvs && py27venv\\Scripts\\activate && python -V && python C:\\jenkins\\workspace\\python_test\\python_venv_pipeline\\Hello_python2.py')


                    //echo "**** Deactivating virtual environments Python 2****"
                    
                    //echo bat(returnStdout: true, script: 'cd pyvenvs && py27venv\\Scripts\\deactivate')

                        
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
                   echo bat(returnStdout: true, script: 'dir')
                   echo bat(returnStdout: true, script: '\\pyvenvs\\py38venv\\Scripts\\activate && \\test_py3\\pytest')
                   echo bat(returnStdout: true, script: 'dir')
                }
            }
        }
    }
        post {
        
        success {
            echo 'Next steps Creating a pip requeriments file, creating new scripts in python 2 and 3, using test on python venvs '
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}



