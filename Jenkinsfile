def remote = [:]
remote.name = 's-VirtualBox'
remote.host = '192.168.1.106'
remote.user = 'root'
remote.password = 'root'
remote.allowAnyHosts = true
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
                    echo 'Clone stage successful'
                }
                failure {
                    echo 'Clone stage failed'
                }
            }
        }
        stage('delete file to server') {
            steps{
                sshRemove remote: remote, path: '/var/www/html/index.html'

            }
         }
        
        stage('Put file to server') {
            steps{
             sshPut remote: remote, from: 'index.html', into: '/var/www/html'
            }
         }
 
        //stage('Deploy'){
            //steps {
              //  sh 'mv index.html /var/www/html'
          //  }
          //  post {
              //  success {
                 //   echo 'Deploy stage successful'
              //  }
              //  failure {
                //    echo 'Deploy stage failed'
               // }
            //}
       // }
    }
}
