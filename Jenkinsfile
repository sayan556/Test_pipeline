pipeline { 
    agent any 
   // options {
       // skipStagesAfterUnstable()
 //   }
    stages {
        stage('Gitclone') { 
            steps { 
                 git credentialsId: 'GIT_HUB_CREDENTIALS', url: 'https://github.com/sayan556/jenkins.git'
            }
        }
        stage('Deploy'){
            steps {
                sh 'mv index.html /var/www/html'
            }
        }
    }
}
