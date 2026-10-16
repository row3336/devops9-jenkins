
pipeline {
    agent any

    stages {
        stage('Install Apache') {
            steps {
                sh 'sudo -n apt-get update'
                sh 'sudo -n apt-get install -y apache2'
                sh 'sudo -n systemctl start apache2'
            }
        }

        stage('Check Apache') {
            steps {
                sh 'systemctl status apache2 --no-pager'
                sh 'curl -I http://localhost'
            }
        }
    }
}
