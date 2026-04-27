pipeline {
    agent any
    environment {
         PYTHON_HOME = "C:\\Program Files\\Python312"
        PATH = "${PYTHON_HOME};${PYTHON_HOME}\\Scripts;${env.PATH}"
    }
    stages {

        stage('Check Python') {
            steps {
                bat '''
               where python >nul 2>&1
                            IF %ERRORLEVEL% EQU 0 (
                            echo Python already installed.
                            python --version
                            
                ) ELSE (
                        echo Python not found.
                        powershell -Command "Invoke-WebRequest -Uri https://www.python.org/ftp/python/3.12.4/python-3.12.4-amd64.exe -OutFile python-installer.exe"
                        start /wait python-installer.exe /quiet  InstallAllUsers=1 PrependPath=1
                  
)

exit /b 0
                '''
            }
        }
         stage('Running python code') {
      steps {
        sh 'python hello.py'
      }
    }
    }
}
