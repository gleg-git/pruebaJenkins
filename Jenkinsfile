pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('List files') {
            steps {
                // Listar los archivos en el directorio para verificar que main.py esté presente
                sh 'ls -al'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Crear un entorno virtual y activar
                    sh 'python3 -m venv venv'
                    sh '. venv/bin/activate'
                    // Instalar dependencias desde requirements.txt
                    sh 'pip install -r requirements.txt'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Activar el entorno virtual
                    sh '. venv/bin/activate'
                    // Ejecutar pruebas con pytest
                    sh 'python3 -m pytest'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Simulación de despliegue
                echo 'Simulando despliegue'
            }
        }
    }
    post {
        always {
            // Limpiar entorno si es necesario
            echo 'Pipeline finalizado.'
        }
    }
}
