pipeline {
    agent any
    stages {

        stage('Check Python') {
            steps {
                bat '''
               where python >nul 2>&1
                            IF %ERRORLEVEL% EQU 0 (
                            echo Python already installed.
                            python --version
                ) ELSE (
                        echo Python not found. Installing...
                    
                        set PYTHON_URL=https://www.python.org/ftp/python/3.12.4/python-3.12.4-amd64.exe
                        set INSTALLER=C:\Program Files\Python312\python_installer.exe
                    
                        powershell -Command "Invoke-WebRequest -Uri %PYTHON_URL% -OutFile %INSTALLER%"
                    
                        %INSTALLER% /quiet InstallAllUsers=1 PrependPath=1 Include_test=0
                    
                        echo Installation completed.
)

exit /b 0
                '''
            }
        }
    }
}
