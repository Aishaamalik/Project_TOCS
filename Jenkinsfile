pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'gcloud compute zones list'
                sh 'gcloud compute scp /var/lib/jenkins/workspace/Tocs-Final_main/index.html root@apache-server:/var/www/html --zone=us-west4-b'
            }
        }
        stage('Verify') {
            steps {
                sh '''
                    ssh root@apache-server --zone=us-west4-b <<EOF
                        ls -l /var/www/html/index.html
                        cat /var/www/html/index.html
                        systemctl status apache2 || systemctl status httpd
                    EOF
                '''
            }
        }
    }
}
