
pipeline {
    agent any

    stages {

        stage('Hello') {
            steps {
                echo 'Hello depuis un pipeline declaratif'
            }
        }

        stage('Infos environnement') {
            steps {
                echo "Nom du noeud Jenkins: ${env.NODE_NAME}"
                echo "Workspace: ${env.WORKSPACE}"
            }
        }

        stage('Installation des dependances') {
            steps {
                bat 'python --version'
                bat 'python -m pip install -r requirements-dev.txt'
            }
        }

        stage('Execution des tests') {
            steps {
                bat 'python -m pytest -v --cov=app --cov-report=term-missing'
            }
        }
    }
}
