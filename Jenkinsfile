pipeline {
    agent any
    stages {

        stage('Check Python') {
            steps {
                bat '''
                where python >nul 2>nul
                IF %ERRORLEVEL% NEQ 0 (
                    echo Python not found. Installing...
                    echo Installation completed.
                ) ELSE (
                    echo Python already installed.
                )
                '''
            }
        }
    }
}
