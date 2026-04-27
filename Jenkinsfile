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

        stage('Verify Python') {
            steps {
                bat 'python --version'
            }
        }

         stage('hello') {
      steps {
        sh 'python hello.py'
      }
    }
    }
}
