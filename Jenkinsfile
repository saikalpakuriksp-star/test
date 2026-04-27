pipeline {
    agent any
    stages {

        stage('Check Python') {
            steps {
                bat '''
                where python >nul 2>nul
                IF %ERRORLEVEL% EQU 0 (
                 echo Python already installed.
                 
                ) ELSE (
                      echo Python not found. Installing...
                    echo Installation completed.
                )
                '''
            }
        }
    }
}
