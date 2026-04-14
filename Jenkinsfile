
pipeline {
    agent any

    stages {

        stage('Clonage') {
            steps {
                git 'https://github.com/JalalBe66/jenkins-test.git'
            }
        }

        stage('Tests') {
            steps {
                sh '''
                    python3 -m venv venv
                    venv/bin/pip install pytest
                    venv/bin/pytest
                '''
            }
        }

        stage('Nettoyage') {
            steps {
                sh 'rm -rf venv'
            }
        }
    }

    post {
        success {
            echo "Pipeline exécuté avec succès."
        }
        failure {
            echo "Pipeline échoué"
        }
    }
}
