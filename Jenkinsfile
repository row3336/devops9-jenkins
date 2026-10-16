
pipeline {
    agent any

    options {
        timeout(time: 15, unit: 'MINUTES')
    }

    stages {
        stage('Install Apache') {
            steps {
                sh 'sudo -n apt-get update'
                sh 'sudo -n apt-get install -y apache2'
            }
        }

        stage('Start Apache') {
            steps {
                sh 'sudo -n systemctl start apache2'
            }
        }

        stage('Check Apache') {
            steps {
                sh 'systemctl is-active --quiet apache2'
                sh 'curl -fI --max-time 10 http://localhost'
            }
        }
    }
}
