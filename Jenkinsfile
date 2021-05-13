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
        stage("SSH Into Server") {
            steps{
                def remote = [:]
            }
            steps{
                remote.name = 's-VirtualBox'
            }
            steps{
                remote.host = '192.168.1.106'
            }
            steps{
                remote.user = 's'
            }
            steps{
                remote.password = 's'
            }
            steps{
                remote.allowAnyHosts = true
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
