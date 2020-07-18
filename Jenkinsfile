node{
   stage('scm checkout'){
   git 'https://github.com/madhuprasadbm/test'
   }
   stage('compile package'){
   def mvnhome = tool name: 'maven3', type: 'maven'
   sh "${mvnhome}/bin/mvn package"
   }
   stage('building package'){
      sshagent(['tomcat']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.32.102:/opt/tomcat/webapps'
}
   }
   
   stage('start tomcat'){
      sshagent(['tomcat']) {
      sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.32.102 "sudo systemctl start tomcat"'
   }
   }
   stage('email notification'){
      mail bcc: '', body: '''HI bro
      test email from jenkins
      Thanks''', cc: '', from: '', replyTo: '', subject: 'Jenkins notification', to: 'madhuprasad.bm@gmail.com'
}
}
   
   
