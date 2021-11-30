pipeline {
    agent any

    stages {
        stage('config') {
            steps {
                sh 'gcloud config list'
                sh 'gcloud config set project midevops'
                sh  'gcloud config set account terraform@midevops.iam.gserviceaccount.com'
                 sh 'gcloud config list'
            }
        }
        
        stage('Deploy ENV') {
            steps {
                sh 'gcloud compute instances $ACTION $Instance --zone us-central1-c --quiet'
            }
        }
        
       
    }
}
