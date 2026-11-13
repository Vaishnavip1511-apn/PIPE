pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: '<paste your repo link here>'
            }
        }
        stage('Compile') {
            steps {
                bat 'python -m py_compile app.py apptest.py'
            }
        }
        stage('Test') {
            steps {
                bat 'python -m unittest apptest -v'
            }
        }
        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }
        stage('Package') {
            steps {
                bat 'tar -a -c -f app.zip app.py apptest.py'
            }
        }
    }
}
