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
                where python >nul 2>nul
                IF %ERRORLEVEL% NEQ 0 (
                    echo Python not found. Installing...
                    
                    powershell -Command "Invoke-WebRequest -Uri https://www.python.org/ftp/python/3.12.4/python-3.12.4-amd64.exe -OutFile python-installer.exe"
                    
                    start /wait python-installer.exe /quiet InstallAllUsers=1 PrependPath=1
                    
                    echo Installation completed.
                ) ELSE (
                    echo Python already installed.
                )
                '''
            }
        }

        stage('Verify Python') {
            steps {
                bat 'python --version'
            }
        }

         stage('hello') {
      steps {
        sh 'python3 hello.py'
      }
    }
    }
}
