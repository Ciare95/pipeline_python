pipeline {
    agent any

    stages {
        stage('Instalar dependencias') {
            steps {
                bat 'pip install -r requirements.txt || echo No hay archivo requirements.txt'
            }
        }
        stage('Ejecutar pruebas') {
            steps {
                bat 'python test_main.py'
            }
        }
    }

    post {
        failure {
            echo 'Ocurrió un error en la ejecución del pipeline.'
        }
        success {
            echo 'Pipeline ejecutado correctamente.'
        }
    }
}
