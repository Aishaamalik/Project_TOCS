pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'gcloud compute zones list'
                sh 'gcloud compute scp /var/lib/jenkins/workspace/Last_Project_main/*.html root@apache-server:/var/www/html --zone=us-west4-b'
            }
        }
    }
}
