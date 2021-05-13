pipeline { 
    agent any 
   // options {
       // skipStagesAfterUnstable()
 //   }
    stages {
        stage('Gitclone') { 
            steps { 
                git branch: 'main', credentialsId: '5a22a18e-6011-429e-971f-9cb1d3b24d20', url: 'https://github.com/sayan556/jenkins.git'
            }
            post {
                success {
                    echo 'Compile stage successful'
                }
                failure {
                    echo 'Compile stage failed'
                }
            }
        }
        stage('Deploy'){
            steps {
                sh 'mv index.html /var/www/html'
            }
        }
    }
}
