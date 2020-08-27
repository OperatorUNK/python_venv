pipeline {
    agent {label 'windows'}
    stages {
        stage('build') {
            steps {
                script {
                    //echo "**************Show env variables *******************"
                    //echo env.PATH
                    //bat 'echo %PATH%'
                    //bat 'wmic computersystem get name'
                    //echo bat(returnStdout: true, script: 'dir')
                    //echo "**************Show Chocolatey help *******************"
                    //echo bat(returnStdout: true, script: 'choco -?')
                    //echo "**************Install python *******************"
                    //echo bat(returnStdout: true, script: 'choco install python -y')
                    echo "************** Run python v2 file *******************"
                    echo bat(returnStdout: true, script: 'cd C:\\jenkins\\workspace\\python_test\\Python2 && py -2 Hello_python2.py')
                    
                    
                    
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
