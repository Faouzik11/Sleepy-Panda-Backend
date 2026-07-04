pipeline {

    agent any

    stages {

        stage('Install Dependencies') {

            steps {

                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install --upgrade pip
                pip install -r requirements-ci.txt
                '''

            }

        }

        stage('Verify') {

            steps {

                sh '''
                . venv/bin/activate
                python --version
                '''

            }

        }

    }

}
