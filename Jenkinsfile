pipeline {
    agent any

    stages {
        stage('Instalar dependencias') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'pip install -r requirements.txt || echo "No hay archivo requirements.txt"'
                    } else {
                        bat 'pip install -r requirements.txt || echo No hay archivo requirements.txt'
                    }
                }
            }
        }
        stage('Ejecutar pruebas') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'python3 test_main.py'
                    } else {
                        bat 'python test_main.py'
                    }
                }
            }
        }
    }
}
