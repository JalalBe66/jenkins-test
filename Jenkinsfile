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
                    pip3 install pytest --break-system-packages
                    python3 -m pytest tests/ -v
                '''
            }
        }
        stage('Nettoyage') {
            steps {
                echo "Nettoyage terminé"
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
