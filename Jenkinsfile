pipeline {

    agent any

    environment {
        DB_USER = credentials('auth_db_user')
        DB_PASS = credentials('auth_db_password')
        DB_NAME = credentials('auth_db_name')
        DB_HOST = credentials('auth_db_host')
        DB_PORT = credentials('auth_db_port')

        SECRET_KEY = credentials('secret_key')

        SMTP_SERVER = credentials('smtp_server')
        SMTP_PORT = credentials('smtp_port')
        EMAIL_SENDER = credentials('email_sender')
        EMAIL_PASSWORD = credentials('email_password')
    }

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
                pip --version

                echo "Environment Loaded Successfully"

                echo "DB_USER=$DB_USER"
                echo "DB_HOST=$DB_HOST"
                echo "DB_NAME=$DB_NAME"
                '''
            }
        }

    }

}
