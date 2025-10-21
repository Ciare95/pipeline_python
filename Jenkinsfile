pipeline {
    agent {
        docker {
            image 'python:3.11'
            args '-u root'
        }
    }

    stages {
        stage('Instalar dependencias') {
            steps {
                sh '''
                    pip install -r requirements.txt || echo "No hay archivo requirements.txt"
                '''
            }
        }

        stage('Ejecutar pruebas') {
            steps {
                sh '''
                    python test_main.py
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline ejecutado correctamente.'
        }
        failure {
            echo 'Ocurrió un error en la ejecución del pipeline.'
        }
    }
}
