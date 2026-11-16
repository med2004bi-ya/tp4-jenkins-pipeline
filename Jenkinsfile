
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
                bat 'C:\Users\DELL\AppData\Local\Programs\Python\Python314\python.exe --version'
                bat 'C:\Users\DELL\AppData\Local\Programs\Python\Python314\python.exe -m pip install -r requirements-dev.txt'
            }
        }

        stage('Execution des tests') {
            steps {
                bat 'C:\Users\DELL\AppData\Local\Programs\Python\Python314\python.exe -m pytest -v --cov=app --cov-report=term-missing'
            }
        }
    }
}
