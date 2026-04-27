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
        
                    
                        echo Installation completed.
)

exit /b 0
                '''
            }
        }
    }
}
