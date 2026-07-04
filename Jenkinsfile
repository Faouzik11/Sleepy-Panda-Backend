pipeline {

    agent any

    stages {

        stage('Install Dependencies') {

            steps {

                sh 'pip3 install -r requirements-ci.txt'

            }

        }

        stage('Verify') {

            steps {

                sh 'python3 --version'

            }

        }

    }

}
